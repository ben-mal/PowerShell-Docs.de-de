---
title: Einführung
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
description: Dies ist die Einleitung des Buchs „PowerShell 101“ von Mike F. Robbins.
ms.openlocfilehash: d85590c2ef34c4e8b5cb7f2707bd9d6dd9b84b89
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501506"
---
# <a name="introduction"></a><span data-ttu-id="d7993-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="d7993-103">Introduction</span></span>

<table>
  <tr><td>
  <a href="https://leanpub.com/powershell101">
  <img src="media/powershell101-150x194.png" alt="PowerShell 101 (the book)" />
  </a>
  </td>
  <td colspan=2>
<span data-ttu-id="d7993-104">Dieser Inhalt erschien ursprünglich im Buch <em>PowerShell 101</em> von Mike F. Robbins.</span><span class="sxs-lookup"><span data-stu-id="d7993-104">This content originally appeared in the book <em>PowerShell 101</em> by Mike F Robbins.</span></span> <span data-ttu-id="d7993-105">Wir danken Mike, dass er uns erlaubt hat, seinen Inhalt hier wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="d7993-105">We thank Mike for granting us permission to reuse his content here.</span></span> <span data-ttu-id="d7993-106">Der Inhalt wurde gegenüber der ursprünglichen Veröffentlichung bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="d7993-106">The content has been edited from the original publication.</span></span> <span data-ttu-id="d7993-107">Das Originalbuch ist weiterhin bei Leanpub unter <a href="https://leanpub.com/powershell101">PowerShell 101</a> erhältlich.</span><span class="sxs-lookup"><span data-stu-id="d7993-107">You can still get the original book from Leanpub at <a href="https://leanpub.com/powershell101">PowerShell 101</a>.</span></span>
  </td></tr>
</table>

## <a name="who-is-this-book-for"></a><span data-ttu-id="d7993-108">An wen richtet sich dieses Buch?</span><span class="sxs-lookup"><span data-stu-id="d7993-108">Who is this book for?</span></span>

<span data-ttu-id="d7993-109">Es handelt sich um ein Buch auf Einsteigerniveau für alle, die sich mit PowerShell vertraut machen möchten.</span><span class="sxs-lookup"><span data-stu-id="d7993-109">This is an entry-level book for anyone wanting to learn PowerShell.</span></span>

<span data-ttu-id="d7993-110">Dieses Buch konzentriert sich auf PowerShell, Version 5.1, die unter Windows 10 und Windows Server 2016 in einer Microsoft Active Directory-Domänenumgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d7993-110">This book focuses on PowerShell version 5.1 running on Windows 10 and Windows Server 2016 in a Microsoft Active Directory domain environment.</span></span> <span data-ttu-id="d7993-111">Die grundlegenden Konzepte gelten jedoch für alle Versionen von PowerShell, die auf einer unterstützten Plattform ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d7993-111">However, the basic concepts apply to all versions of PowerShell running on any supported platform.</span></span>

## <a name="about-this-book"></a><span data-ttu-id="d7993-112">Zu diesem Buch</span><span class="sxs-lookup"><span data-stu-id="d7993-112">About this book</span></span>

<span data-ttu-id="d7993-113">Dieses Buch ist eine Sammlung der Informationen, deren Kenntnis ich mir gewünscht hätte, als ich begonnen habe, mich mit PowerShell zu beschäftigen, sowie von Tipps, Tricks und bewährten Methoden, die ich bei der Verwendung von PowerShell während der letzten 10 Jahre gesammelt habe.</span><span class="sxs-lookup"><span data-stu-id="d7993-113">This book is a collection of what I wish someone would have told me when I started learning PowerShell, along with the tips, tricks, and best practices that I've learned while using PowerShell during the past 10 years.</span></span>

<span data-ttu-id="d7993-114">Statt eine große Menge an Informationen bereitzustellen, versucht dieses Buch, das Gleichgewicht bei der Bereitstellung genau der ausreichenden Informationen für jemanden zu finden, der gerade erst mit der Verwendung von PowerShell beginnt.</span><span class="sxs-lookup"><span data-stu-id="d7993-114">Instead of providing an enormous amount of information, this book attempts to provide a balance of enough information to be successful for someone who is just getting started with PowerShell.</span></span> <span data-ttu-id="d7993-115">Jedes Kapitel enthält Links zu spezifischen Hilfethemen, für diejenigen, die weitere Informationen zu den in dem jeweiligen Kapitel behandelten Themen wünschen.</span><span class="sxs-lookup"><span data-stu-id="d7993-115">Each chapter contains links to specific help topics for those who want more information about the topics covered in that chapter.</span></span>

## <a name="about-the-author"></a><span data-ttu-id="d7993-116">Zum Autor</span><span class="sxs-lookup"><span data-stu-id="d7993-116">About the author</span></span>

<span data-ttu-id="d7993-117">Mike F. Robbins ist ein ehemaliger Microsoft MVP, Mitautor von _Windows PowerShell TFM, 4. Ausgabe_ , sowie mitwirkender Autor des Buchs _PowerShell Deep Dives_ .</span><span class="sxs-lookup"><span data-stu-id="d7993-117">Mike F Robbins is a former Microsoft MVP, co-author of _Windows PowerShell TFM 4th Edition_ , and a contributing author in the _PowerShell Deep Dives_ book.</span></span> <span data-ttu-id="d7993-118">Mike war ein starker Unterstützer der PowerShell-Community und ist jetzt Hauptautor für [Azure PowerShell][] bei Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d7993-118">Mike has been a strong supporter of the PowerShell community and is now the lead writer for [Azure PowerShell][] at Microsoft.</span></span> <span data-ttu-id="d7993-119">Er bloggt auf [mikefrobbins.com][] und ist bei Twitter unter [@mikefrobbins][] zu finden.</span><span class="sxs-lookup"><span data-stu-id="d7993-119">He blogs at [mikefrobbins.com][] and can be found on twitter [@mikefrobbins][].</span></span>

## <a name="lab-environment"></a><span data-ttu-id="d7993-120">Laborumgebung</span><span class="sxs-lookup"><span data-stu-id="d7993-120">Lab environment</span></span>

<span data-ttu-id="d7993-121">Die Beispiele in diesem Buch wurden unter Windows 10 Anniversary Edition (Build 1607) und Windows Server 2016 unter Verwendung von PowerShell, Version 5.1, entworfen und getestet.</span><span class="sxs-lookup"><span data-stu-id="d7993-121">The examples in this book were designed and tested on Windows 10 Anniversary Edition (build 1607) and Windows Server 2016 using PowerShell version 5.1.</span></span> <span data-ttu-id="d7993-122">Wenn Sie eine andere Version von PowerShell oder des Betriebssystems verwenden, können sich Ihre Ergebnisse von den hier gezeigten unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d7993-122">If you're using a different version of PowerShell or operating system, your results may differ from those shown here.</span></span>

<!-- link references -->
[@mikefrobbins]: https://twitter.com/mikefrobbins
[mikefrobbins.com]: http://mikefrobbins.com/
[PowerShell 101]: https://leanpub.com/powershell101
[Azure PowerShell]: /powershell/azure
