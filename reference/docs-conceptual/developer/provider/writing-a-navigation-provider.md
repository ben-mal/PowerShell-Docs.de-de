---
ms.date: 09/13/2016
ms.topic: reference
title: Schreiben eines Navigationsanbieters
description: Schreiben eines Navigationsanbieters
ms.openlocfilehash: 3123672d3365c97714557bd0e72a6e444ac228a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355220"
---
# <a name="writing-a-navigation-provider"></a><span data-ttu-id="f438c-103">Schreiben eines Navigationsanbieters</span><span class="sxs-lookup"><span data-stu-id="f438c-103">Writing a navigation provider</span></span>

<span data-ttu-id="f438c-104">In diesem Thema wird beschrieben, wie die Methoden eines Windows PowerShell-Anbieters implementiert werden, die die Unterstützung von schsted Containern (Datenspeicher mit mehreren Ebenen), das Verschieben von Elementen und relative Pfade unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f438c-104">This topic describes how to implement the methods of a Windows PowerShell provider that support nested containers (multi-level data stores), moving items, and relative paths.</span></span> <span data-ttu-id="f438c-105">Ein Navigations Anbieter muss von der [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="f438c-105">A navigation provider must derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="f438c-106">Für den Anbieter in den Beispielen in diesem Thema wird eine Access-Datenbank als Datenspeicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="f438c-106">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="f438c-107">Es gibt mehrere Hilfsmethoden und-Klassen, die für die Interaktion mit der Datenbank verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f438c-107">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="f438c-108">Das komplette Beispiel, das die-Hilfsmethoden enthält, finden Sie unter [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="f438c-108">For the complete sample that includes the helper methods, see [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>

<span data-ttu-id="f438c-109">Weitere Informationen zu Windows PowerShell-Anbietern finden Sie unter Übersicht über den [Windows PowerShell-Anbieter](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f438c-109">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-navigation-methods"></a><span data-ttu-id="f438c-110">Implementieren von Navigationsmethoden</span><span class="sxs-lookup"><span data-stu-id="f438c-110">Implementing navigation methods</span></span>

<span data-ttu-id="f438c-111">Die [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse implementiert Methoden, die die Unterstützung von unterstützten Containern, relativen Pfaden und Verschiebungs Elementen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f438c-111">The [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class implements methods that support nested containers, relative paths, and moving items.</span></span> <span data-ttu-id="f438c-112">Eine umfassende Liste dieser Methoden finden Sie unter [navigationcmdletprovider-Methoden](/dotnet/api/system.management.automation.provider.navigationcmdletprovider#methods).</span><span class="sxs-lookup"><span data-stu-id="f438c-112">For a complete list of these methods, see [NavigationCmdletProvider Methods](/dotnet/api/system.management.automation.provider.navigationcmdletprovider#methods).</span></span>

> [!NOTE]
> <span data-ttu-id="f438c-113">Dieses Thema baut auf den Informationen in der Schnellstartanleitung für den [Windows PowerShell-Anbieter](./windows-powershell-provider-quickstart.md)auf.</span><span class="sxs-lookup"><span data-stu-id="f438c-113">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="f438c-114">Dieses Thema behandelt nicht die Grundlagen der Einrichtung eines Anbieter Projekts oder die Implementierung der Methoden, die von der [System. Management. Automation. Provider. drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) -Klasse geerbt werden, die Laufwerke erstellt und entfernt.</span><span class="sxs-lookup"><span data-stu-id="f438c-114">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span> <span data-ttu-id="f438c-115">Außerdem wird in diesem Thema nicht behandelt, wie Methoden implementiert werden, die von der [System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse oder der [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f438c-115">This topic also does not cover how to implement methods exposed by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) or [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) classes.</span></span> <span data-ttu-id="f438c-116">Ein Beispiel, das zeigt, wie Item-Cmdlets implementiert werden, finden Sie unter [Schreiben eines Element Anbieters](./writing-an-item-provider.md).</span><span class="sxs-lookup"><span data-stu-id="f438c-116">For an example that shows how to implement item cmdlets, see [Writing an item provider](./writing-an-item-provider.md).</span></span> <span data-ttu-id="f438c-117">Ein Beispiel für das Implementieren von Container-Cmdlets finden Sie unter [Schreiben eines Container Anbieters](./writing-a-container-provider.md).</span><span class="sxs-lookup"><span data-stu-id="f438c-117">For an example that shows how to implement container cmdlets, see [Writing a container provider](./writing-a-container-provider.md).</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="f438c-118">Deklarieren der Anbieter Klasse</span><span class="sxs-lookup"><span data-stu-id="f438c-118">Declaring the provider class</span></span>

<span data-ttu-id="f438c-119">Deklarieren Sie den Anbieter so, dass er von der [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse abgeleitet wird, und versehen Sie ihn mit dem [System. Management. Automation. Provider. cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span><span class="sxs-lookup"><span data-stu-id="f438c-119">Declare the provider to derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : NavigationCmdletProvider
   {

   }
```

### <a name="implementing-isitemcontainer"></a><span data-ttu-id="f438c-120">Implementieren von isitemcontainer</span><span class="sxs-lookup"><span data-stu-id="f438c-120">Implementing IsItemContainer</span></span>

<span data-ttu-id="f438c-121">Die [System. Management. Automation. Provider. navigationcmdletprovider. isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) -Methode überprüft, ob das Element im angegebenen Pfad ein Container ist.</span><span class="sxs-lookup"><span data-stu-id="f438c-121">The [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method checks whether the item at the specified path is a container.</span></span>

```csharp
protected override bool IsItemContainer(string path)
      {
         if (PathIsDrive(path))
         {
             return true;
         }

         string[] pathChunks = ChunkPath(path);
         string tableName;
         int rowNumber;

         PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

         if (type == PathType.Table)
         {
            foreach (DatabaseTableInfo ti in GetTables())
            {
                if (string.Equals(ti.Name, tableName, StringComparison.OrdinalIgnoreCase))
                {
                    return true;
                }
            } // foreach (DatabaseTableInfo...
         } // if (pathChunks...

         return false;
      }
```

### <a name="implementing-getchildname"></a><span data-ttu-id="f438c-122">Implementieren von "getchildname"</span><span class="sxs-lookup"><span data-stu-id="f438c-122">Implementing GetChildName</span></span>

<span data-ttu-id="f438c-123">Die [System. Management. Automation. Provider. navigationcmdletprovider. getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) -Methode ruft die Name-Eigenschaft des untergeordneten Elements im angegebenen Pfad ab.</span><span class="sxs-lookup"><span data-stu-id="f438c-123">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method gets the name property of the child item at the specified path.</span></span> <span data-ttu-id="f438c-124">Wenn das Element im angegebenen Pfad kein untergeordnetes Element eines Containers ist, sollte diese Methode den Pfad zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f438c-124">If the item at the specified path is not a child of a container, then this method should return the path.</span></span>

```csharp
protected override string GetChildName(string path)
       {
           if (PathIsDrive(path))
           {
               return path;
           }

           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               return tableName;
           }
           else if (type == PathType.Row)
           {
               return rowNumber.ToString(CultureInfo.CurrentCulture);
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

           return null;
       }
```

### <a name="implementing-getparentpath"></a><span data-ttu-id="f438c-125">Implementieren von getcentpath</span><span class="sxs-lookup"><span data-stu-id="f438c-125">Implementing GetParentPath</span></span>

<span data-ttu-id="f438c-126">Mit der [System. Management. Automation. Provider. navigationcmdletprovider. getparameentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) -Methode wird der Pfad des übergeordneten Elements des Elements im angegebenen Pfad abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f438c-126">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method gets the path of the parent of the item at the specified path.</span></span> <span data-ttu-id="f438c-127">Wenn das Element im angegebenen Pfad der Stamm des Datenspeicher ist (d. h., es ist kein übergeordnetes Element), sollte diese Methode den Stammpfad zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f438c-127">If the item at the specified path is the root of the data store (so it has no parent), then this method should return the root path.</span></span>

```csharp
protected override string GetParentPath(string path, string root)
       {
           // If root is specified then the path has to contain
           // the root. If not nothing should be returned
           if (!String.IsNullOrEmpty(root))
           {
               if (!path.Contains(root))
               {
                   return null;
               }
           }

           return path.Substring(0, path.LastIndexOf(pathSeparator, StringComparison.OrdinalIgnoreCase));
       }
```

### <a name="implementing-makepath"></a><span data-ttu-id="f438c-128">Implementieren von makepath</span><span class="sxs-lookup"><span data-stu-id="f438c-128">Implementing MakePath</span></span>

<span data-ttu-id="f438c-129">Die [System. Management. Automation. Provider. navigationcmdletprovider. makepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) -Methode verbindet einen angegebenen übergeordneten Pfad und einen angegebenen untergeordneten Pfad, um einen Anbieter internen Pfad zu erstellen (Weitere Informationen zu Pfad Typen, die Anbieter unterstützen können, finden Sie unter [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f438c-129">The [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method joins a specified parent path and a specified child path to create a provider-internal path (for information about path types that providers can support, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="f438c-130">Die PowerShell-Engine ruft diese Methode auf, wenn ein Benutzer das [Microsoft. PowerShell. Commands. joinpathcommand](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) -Cmdlet aufruft.</span><span class="sxs-lookup"><span data-stu-id="f438c-130">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.JoinPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) cmdlet.</span></span>

```csharp
protected override string MakePath(string parent, string child)
       {
           string result;

           string normalParent = NormalizePath(parent);
           normalParent = RemoveDriveFromPath(normalParent);
           string normalChild = NormalizePath(child);
           normalChild = RemoveDriveFromPath(normalChild);

           if (String.IsNullOrEmpty(normalParent) && String.IsNullOrEmpty(normalChild))
           {
               result = String.Empty;
           }
           else if (String.IsNullOrEmpty(normalParent) && !String.IsNullOrEmpty(normalChild))
           {
               result = normalChild;
           }
           else if (!String.IsNullOrEmpty(normalParent) && String.IsNullOrEmpty(normalChild))
           {
               if (normalParent.EndsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result = normalParent;
               }
               else
               {
                   result = normalParent + pathSeparator;
               }
           } // else if (!String...
           else
           {
               if (!normalParent.Equals(String.Empty) &&
                   !normalParent.EndsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result = normalParent + pathSeparator;
               }
               else
               {
                   result = normalParent;
               }

               if (normalChild.StartsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result += normalChild.Substring(1);
               }
               else
               {
                   result += normalChild;
               }
           } // else

           return result;
       }
```

### <a name="implementing-normalizerelativepath"></a><span data-ttu-id="f438c-131">Implementieren von normalizerelativepath</span><span class="sxs-lookup"><span data-stu-id="f438c-131">Implementing NormalizeRelativePath</span></span>

<span data-ttu-id="f438c-132">Die [System. Management. Automation. Provider. navigationcmdletprovider. normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) -Methode nimmt `path` -und- `basepath` Parameter an und gibt einen normalisierten Pfad zurück, der dem `path` -Parameter und relativ zum- `basepath` Parameter entspricht.</span><span class="sxs-lookup"><span data-stu-id="f438c-132">The [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method takes `path` and `basepath` parameters, and returns a normalized path that is equivalent to the `path` parameter and relative to the `basepath` parameter.</span></span>

```csharp
protected override string NormalizeRelativePath(string path,
                                                            string basepath)
       {
           // Normalize the paths first
           string normalPath = NormalizePath(path);
           normalPath = RemoveDriveFromPath(normalPath);
           string normalBasePath = NormalizePath(basepath);
           normalBasePath = RemoveDriveFromPath(normalBasePath);

           if (String.IsNullOrEmpty(normalBasePath))
           {
               return normalPath;
           }
           else
           {
               if (!normalPath.Contains(normalBasePath))
               {
                   return null;
               }

               return normalPath.Substring(normalBasePath.Length + pathSeparator.Length);
           }
       }
```

### <a name="implementing-moveitem"></a><span data-ttu-id="f438c-133">Implementieren von "muveitem"</span><span class="sxs-lookup"><span data-stu-id="f438c-133">Implementing MoveItem</span></span>

<span data-ttu-id="f438c-134">Die [System. Management. Automation. Provider. navigationcmdletprovider. muveitem \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) -Methode verschiebt ein Element aus dem angegebenen Pfad in den angegebenen Zielpfad.</span><span class="sxs-lookup"><span data-stu-id="f438c-134">The [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method moves an item from the specified path to the specified destination path.</span></span> <span data-ttu-id="f438c-135">Die PowerShell-Engine ruft diese Methode auf, wenn ein Benutzer das Cmdlet " [Microsoft. PowerShell. Commands.](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) -Cmdlet" aufruft.</span><span class="sxs-lookup"><span data-stu-id="f438c-135">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.MoveItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) cmdlet.</span></span>

```csharp
protected override void MoveItem(string path, string destination)
       {
           // Get type, table name and rowNumber from the path
           string tableName, destTableName;
           int rowNumber, destRowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           PathType destType = GetNamesFromPath(destination, out destTableName,
                                    out destRowNumber);

           if (type == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(path);
           }

           if (destType == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(destination);
           }

           if (type == PathType.Table)
           {
               ArgumentException e = new ArgumentException("Move not supported for tables");

               WriteError(new ErrorRecord(e, "MoveNotSupported",
                   ErrorCategory.InvalidArgument, path));

               throw e;
           }
           else
           {
               OdbcDataAdapter da = GetAdapterForTable(tableName);
               if (da == null)
               {
                   return;
               }

               DataSet ds = GetDataSetForTable(da, tableName);
               DataTable table = GetDataTable(ds, tableName);

               OdbcDataAdapter dda = GetAdapterForTable(destTableName);
               if (dda == null)
               {
                   return;
               }

               DataSet dds = GetDataSetForTable(dda, destTableName);
               DataTable destTable = GetDataTable(dds, destTableName);
               DataRow row = table.Rows[rowNumber];

               if (destType == PathType.Table)
               {
                   DataRow destRow = destTable.NewRow();

                   destRow.ItemArray = row.ItemArray;
               }
               else
               {
                   DataRow destRow = destTable.Rows[destRowNumber];

                   destRow.ItemArray = row.ItemArray;
               }

               // Update the changes
               if (ShouldProcess(path, "MoveItem"))
               {
                   WriteItemObject(row, path, false);
                   dda.Update(dds, destTableName);
               }
           }
       }
```

## <a name="see-also"></a><span data-ttu-id="f438c-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f438c-136">See Also</span></span>

[<span data-ttu-id="f438c-137">Schreiben eines Containeranbieters</span><span class="sxs-lookup"><span data-stu-id="f438c-137">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="f438c-138">Windows PowerShell-Anbieter: Übersicht</span><span class="sxs-lookup"><span data-stu-id="f438c-138">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)
