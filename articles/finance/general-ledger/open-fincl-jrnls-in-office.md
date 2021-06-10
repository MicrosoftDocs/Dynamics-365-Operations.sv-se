---
title: Öppna mallar för redovisningsjournaler i Office
description: Detta ämne beskriver problem som kan uppstå när du skapar anpassade redovisningsjournaler genom att använda en mall i Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0773f47551b2460ec310b92b67c634b433147749
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "6089467"
---
# <a name="open-financial-journal-templates-in-office"></a><span data-ttu-id="d8d7b-103">Öppna mallar för redovisningsjournaler i Office</span><span class="sxs-lookup"><span data-stu-id="d8d7b-103">Open financial journal templates in Office</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8d7b-104">Detta ämne beskriver problem som kan uppstå när du skapar anpassade redovisningsjournaler genom att använda en mall i Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-104">This topic describes issues that might occur when you create custom financial journals by using a Microsoft Excel template.</span></span>

## <a name="symptom"></a><span data-ttu-id="d8d7b-105">Symptom</span><span class="sxs-lookup"><span data-stu-id="d8d7b-105">Symptom</span></span>

<span data-ttu-id="d8d7b-106">Du har skapat en anpassad Excel-mall för redovisningsjournaler, men den visas inte på menyn **Öppna rader i Excel**.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-106">You created a custom Excel template for financial journals, but it doesn't appear on the **Open lines in Excel** menu.</span></span> <span data-ttu-id="d8d7b-107">Eller så visas den på menyn, men en annan mall öppnas när du väljer den.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-107">Alternatively, it does appear on the menu, a different template is opened but when you select it.</span></span>

## <a name="resolution"></a><span data-ttu-id="d8d7b-108">Lösning</span><span class="sxs-lookup"><span data-stu-id="d8d7b-108">Resolution</span></span>

<span data-ttu-id="d8d7b-109">Standardfunktionen Öppna i Excel använder rotdatakällan (tabell) för den aktuella sidan för att bestämma vilka Office-mallar eller datatabeller som visas som alternativ på menyn **Öppna i Excel**.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-109">The default Open in Excel functionality uses the root data source (table) of the current page to determine which Office templates or data entities appear as options on the **Open in Excel** menu.</span></span> <span data-ttu-id="d8d7b-110">Detta beteende är inte optimalt för redovisningsjournaler, eftersom redovisningsjournaler använder sig av samma tabeller (LedgerJournalTable och LedgerJournalTrans) som rotdatakällan till många andra typer av journaler.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-110">This behavior isn't an ideal experience for financial journals, because financial journals use the same tables (LedgerJournalTable and LedgerJournalTrans) as the root data source of many other types of journals.</span></span>

<span data-ttu-id="d8d7b-111">För redovisningsjournaler är funktionen Öppna i Excel avsedd för att visa mallar som har utformats för journalen som du för närvarande arbetar i kontexten av, som till exempel den allmänna journalen eller en betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-111">For financial journals, the Open Lines in Excel functionality is intended to show templates that are designed for the journal that you're currently working in the context of, such as the general journal or a payment journal.</span></span> <span data-ttu-id="d8d7b-112">Exempelvis kommer en mall som är avsedd att användas med en betalningsjournal för leverantörer att utformas för att framtvinga ditt huvudkonto som ett leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-112">For example, a template that is intended to be used with a vendor payment journal will be designed to enforce your primary account as a vendor account.</span></span>

<span data-ttu-id="d8d7b-113">Om du vill framhäva en mall så att den finns tillgänglig på menyerna **Öppna rader i Excel** och **Öppna i Excel**, då kan du enkelt som utvecklare implementera gränssnittet **LedgerIJournalExcelTemplate** och utöka klassen **DocuTemplateRegistrationBase**.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-113">If you want to promote a template so that it's available on the **Open lines in Excel** and **Open in Excel** menus, an easy developer experience is to implement the **LedgerIJournalExcelTemplate** interface and extend the **DocuTemplateRegistrationBase** class.</span></span> <span data-ttu-id="d8d7b-114">Det finns flera exempel på detta tillvägagångssätt implementerat i systemet.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-114">Many examples of this approach are implemented in the system.</span></span> <span data-ttu-id="d8d7b-115">Ett exempel som kan användas som referens är gränssnittet **LedgerDailyJournalExcelTemplate** som skapades för den allmänna journalen (eller dagliga journalen).</span><span class="sxs-lookup"><span data-stu-id="d8d7b-115">One example that can be used for reference is the **LedgerDailyJournalExcelTemplate** interface that was created for the general journal (or daily journal).</span></span>

<span data-ttu-id="d8d7b-116">När gränssnittet **LedgerIJournalExcelTemplate** har implementerats för din mall, kommer menyn **Öppna rader i Excel** att filtrera mallar efter journaltypen på din journal och bara visa mallarna som finns tillgängliga för den journalen.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-116">When the **LedgerIJournalExcelTemplate** interface is implemented for your template, the **Open Lines in Excel** menu will filter templates by the journal type of your journal and will show only the templates that are available for that journal.</span></span> <span data-ttu-id="d8d7b-117">Gränssnittet ger också en valideringsmetod som säkerställer att en mall inte kan öppnas för en journal om den inte uppfyller kraven på kontotyp.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-117">The interface also provides a validation method that ensures that a template can't be opened for a journal if it doesn't meet the account type requirements.</span></span> <span data-ttu-id="d8d7b-118">Du kan till exempel ange att kontotypen måste vara av typen **Leverantör** eller **Redovisning**.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-118">For example, you can specify that the account type must be of the **Vendor** or **Ledger** type.</span></span>

<span data-ttu-id="d8d7b-119">Mer information om den här funktionen finns i [Lägga till mallar på menyn Öppna rader i Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span><span class="sxs-lookup"><span data-stu-id="d8d7b-119">For more information about this functionality, see [Add templates to the Open lines in Excel menu](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span></span>
