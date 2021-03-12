---
title: Översikt över avancerad bankavstämning
description: Det här avsnittet beskriver flödet för den avancerade bankavstämningsprocessen. Med hjälp av den avancerade bankavstämningsfunktionen kan du importera bankutdrag som kan vara automatiskt avstämda inom banktransaktioner.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09128f33d4208bc5c987683bb881aa1129b0dc8e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985446"
---
# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="6b067-104">Översikt över avancerad bankavstämning</span><span class="sxs-lookup"><span data-stu-id="6b067-104">Advanced bank reconciliation overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b067-105">Det här avsnittet beskriver flödet för den avancerade bankavstämningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="6b067-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="6b067-106">Med hjälp av den avancerade bankavstämningsfunktionen kan du importera bankutdrag som kan vara automatiskt avstämda inom banktransaktioner.</span><span class="sxs-lookup"><span data-stu-id="6b067-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="6b067-107">Den avancerade bankavstämningsfunktionen gör att du kan importera bankutdrag.</span><span class="sxs-lookup"><span data-stu-id="6b067-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="6b067-108">Det importerade bankutdraget kan sedan automatiskt stämmas av från banktransaktioner.</span><span class="sxs-lookup"><span data-stu-id="6b067-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="6b067-109">Här följer stegen i flödet för avancerad bankavstämning.</span><span class="sxs-lookup"><span data-stu-id="6b067-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="6b067-110">Ställ in import av bankutdrag.</span><span class="sxs-lookup"><span data-stu-id="6b067-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="6b067-111">Importera bankutdrag via datatabellsramverket.</span><span class="sxs-lookup"><span data-stu-id="6b067-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="6b067-112">Tre vanligaste bankutdragformat är inbyggda i: ISO20022, BAI2 och MT940.</span><span class="sxs-lookup"><span data-stu-id="6b067-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="6b067-113">Funktionen kan utökas till alla format.</span><span class="sxs-lookup"><span data-stu-id="6b067-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="6b067-114">Ställ in en nummerserie som ska användas för avancerad bankavstämning och definiera matchningsregler för bankavstämning.</span><span class="sxs-lookup"><span data-stu-id="6b067-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="6b067-115">Avstämningsmatchningsregler är en uppsättning kriterier som används för att filtrera bankutdragsrader och bankdokumentrader för Microsoft Dynamics 365 Finance under avstämningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="6b067-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 Finance bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="6b067-116">Du kan ställa in mer än en matchningsregel att automatisera och optimera din avstämningsprocess beroende på din affärsverksamhet.</span><span class="sxs-lookup"><span data-stu-id="6b067-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="6b067-117">Stäm av bankutdragen med banktransaktioner för Finance.</span><span class="sxs-lookup"><span data-stu-id="6b067-117">Reconcile bank statements with Finance bank transactions.</span></span>
    -   <span data-ttu-id="6b067-118">Utför automatisk matchning och genereringen av avstämningsjournaler.</span><span class="sxs-lookup"><span data-stu-id="6b067-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="6b067-119">Visa bankutdrag och Finance-banktransaktioner sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="6b067-119">View bank statements and Finance bank transactions side by side.</span></span>
    -   <span data-ttu-id="6b067-120">Bokför Finance-banktransaktioner automatiskt om de visas på ett bankutdrag men inte i Finance-appen.</span><span class="sxs-lookup"><span data-stu-id="6b067-120">Automatically post Finance bank transactions if they appear on a bank statement but don't appear in the Finance app.</span></span>
    -   <span data-ttu-id="6b067-121">Generera ett avstämningsutdrag.</span><span class="sxs-lookup"><span data-stu-id="6b067-121">Generate a reconciliation statement.</span></span>





