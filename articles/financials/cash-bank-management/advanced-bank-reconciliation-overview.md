---
title: "Översikt över avancerad bankavstämning"
description: "Det här avsnittet beskriver flödet för den avancerade bankavstämningsprocessen. Med hjälp av den avancerade bankavstämningsfunktionen kan du importera bankutdrag som kan vara automatiskt avstämda inom banktransaktioner."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 33150777222faa97af7488c59ab13cb0fb9e8e2c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="5406d-104">Översikt över avancerad bankavstämning</span><span class="sxs-lookup"><span data-stu-id="5406d-104">Advanced bank reconciliation overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5406d-105">Det här avsnittet beskriver flödet för den avancerade bankavstämningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5406d-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="5406d-106">Med hjälp av den avancerade bankavstämningsfunktionen kan du importera bankutdrag som kan vara automatiskt avstämda inom banktransaktioner.</span><span class="sxs-lookup"><span data-stu-id="5406d-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="5406d-107">Den avancerade bankavstämningsfunktionen gör att du kan importera bankutdrag.</span><span class="sxs-lookup"><span data-stu-id="5406d-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="5406d-108">Det importerade bankutdraget kan sedan automatiskt stämmas av från banktransaktioner.</span><span class="sxs-lookup"><span data-stu-id="5406d-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="5406d-109">Här följer stegen i flödet för avancerad bankavstämning.</span><span class="sxs-lookup"><span data-stu-id="5406d-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="5406d-110">Ställ in import av bankutdrag.</span><span class="sxs-lookup"><span data-stu-id="5406d-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="5406d-111">Importera bankutdrag via datatabellsramverket.</span><span class="sxs-lookup"><span data-stu-id="5406d-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="5406d-112">Tre vanligaste bankutdragformat är inbyggda i: ISO20022, BAI2 och MT940.</span><span class="sxs-lookup"><span data-stu-id="5406d-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="5406d-113">Funktionen kan utökas till alla format.</span><span class="sxs-lookup"><span data-stu-id="5406d-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="5406d-114">Ställ in en nummerserie som ska användas för avancerad bankavstämning och definiera matchningsregler för bankavstämning.</span><span class="sxs-lookup"><span data-stu-id="5406d-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="5406d-115">En regel för avstämningsmatchning är en uppsättning villkor som används för att filtrera bankutdragsrader och transaktionsrader för Microsoft Dynamics 365 for Finance and Operations, Enterprise edition under avstämningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5406d-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 for Finance and Operations, Enterprise edition bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="5406d-116">Du kan ställa in mer än en matchningsregel att automatisera och optimera din avstämningsprocess beroende på din affärsverksamhet.</span><span class="sxs-lookup"><span data-stu-id="5406d-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="5406d-117">Stäm av bankutdragen med banktransaktioner för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5406d-117">Reconcile bank statements with Finance and Operations bank transactions.</span></span>
    -   <span data-ttu-id="5406d-118">Utför automatisk matchning och genereringen av avstämningsjournaler.</span><span class="sxs-lookup"><span data-stu-id="5406d-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="5406d-119">Visa bankutdrag och Finance and Operations-banktransaktioner sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="5406d-119">View bank statements and Finance and Operations bank transactions side by side.</span></span>
    -   <span data-ttu-id="5406d-120">Bokför Finance and Operations-banktransaktioner automatiskt om de visas på ett bankutdrag men inte i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5406d-120">Automatically post Finance and Operations bank transactions if they appear on a bank statement but don't appear in Finance and Operations.</span></span>
    -   <span data-ttu-id="5406d-121">Generera ett avstämningsutdrag.</span><span class="sxs-lookup"><span data-stu-id="5406d-121">Generate a reconciliation statement.</span></span>






