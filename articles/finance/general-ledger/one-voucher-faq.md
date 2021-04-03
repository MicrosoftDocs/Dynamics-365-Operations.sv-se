---
title: Frågor och svar om en verifikation
description: Detta ämne besvarar vanliga frågor om funktionen En verifikation. En verifikation för redovisningsjournaler (allmän journal, journal för anläggningstillgångar, leverantörsbetalningsjournal och så vidare) låter dig ange flera redovisningsjournaltransaktioner i samband med en enda verifikation.
author: kweekley
manager: AnnBe
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerParameters, AssetProposalDepreciation
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: a0cbc9e1f70bd41157e2ed70f78c8129671a6a04
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234175"
---
# <a name="one-voucher-faq"></a><span data-ttu-id="78234-104">Frågor och svar om En verifikation</span><span class="sxs-lookup"><span data-stu-id="78234-104">One voucher FAQ</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78234-105">Detta ämne besvarar vanliga frågor om funktionen En verifikation.</span><span class="sxs-lookup"><span data-stu-id="78234-105">This topic answers frequently asked questions about the One voucher functionality.</span></span> <span data-ttu-id="78234-106">Me En verifikation för redovisningsjournaler kan du registrera flera underredovisningstransaktioner som en enda verifikation.</span><span class="sxs-lookup"><span data-stu-id="78234-106">One voucher for financial journals lets you enter multiple subledger transactions in the context of a single voucher.</span></span> <span data-ttu-id="78234-107">Journalerna som du kan inkludera i den verifikationen kan vara allmänna journaler, journaler för anläggningstillgångar och leverantörsbetalningsjournaler, bland annat.</span><span class="sxs-lookup"><span data-stu-id="78234-107">The journals that you can include in that voucher can be general journals, fixed asset journals, and vendor payment journals, among others.</span></span>

## <a name="when-will-the-one-voucher-functionality-be-deprecated"></a><span data-ttu-id="78234-108">När blir funktionen En verifikation inaktuell?</span><span class="sxs-lookup"><span data-stu-id="78234-108">When will the One voucher functionality be deprecated?</span></span>

<span data-ttu-id="78234-109">Även om Microsoft inte kan ge en korrekt uppskattning av när funktionen En verifikation kommer att avaktiveras, kommer det troligen att infalla minst två år innan avskrivningen sker.</span><span class="sxs-lookup"><span data-stu-id="78234-109">Although Microsoft can't provide an accurate estimate about when the One voucher functionality will be deprecated, it will likely be at least two years before the deprecation occurs.</span></span>

<span data-ttu-id="78234-110">Som noteras i dokumentationen för En verifikation kan ett antal affärsbehov endast uppfyllas genom att du använder En verifikation.</span><span class="sxs-lookup"><span data-stu-id="78234-110">As is noted in the One voucher documentation, numerous business requirements can be met only by using One voucher.</span></span> <span data-ttu-id="78234-111">Microsoft måste se till att alla identifierade affärsbehov fortfarande kan uppfyllas i systemet efter att funktionen har avskaffats.</span><span class="sxs-lookup"><span data-stu-id="78234-111">Microsoft must ensure that all the identified business requirements can still be met in the system after the functionality is deprecated.</span></span> <span data-ttu-id="78234-112">Därför måste nya funktioner troligen läggas till för att fylla i funktionella luckor.</span><span class="sxs-lookup"><span data-stu-id="78234-112">Therefore, new features will probably have to be added to fill functional gaps.</span></span>

<span data-ttu-id="78234-113">När alla funktionella luckor har fyllts i meddelar Microsoft att funktionen kommer att avaktiveras.</span><span class="sxs-lookup"><span data-stu-id="78234-113">After all functional gaps are filled, Microsoft will communicate that the feature will be deprecated.</span></span> <span data-ttu-id="78234-114">Avskaffandet kommer dock inte att gälla under minst ett år efter det beskedet.</span><span class="sxs-lookup"><span data-stu-id="78234-114">However, the deprecation won't be effective for least one year after that communication.</span></span>

<span data-ttu-id="78234-115">Mer information finns i [Dokumentationen för En verifikation](one-voucher.md).</span><span class="sxs-lookup"><span data-stu-id="78234-115">For more information, see the [One voucher documentation](one-voucher.md).</span></span>

## <a name="what-will-the-solution-that-replaces-one-voucher-look-like"></a><span data-ttu-id="78234-116">Hur kommer lösningen som ersätter En verifikation att se ut?</span><span class="sxs-lookup"><span data-stu-id="78234-116">What will the solution that replaces One voucher look like?</span></span>

<span data-ttu-id="78234-117">Microsoft kan inte skapa en specifik lösning eftersom varje funktionslucka är unik och måste utvärderas utifrån verksamhetens krav.</span><span class="sxs-lookup"><span data-stu-id="78234-117">Microsoft can't provide a specific solution, because each feature gap is different and must be evaluated based on the business requirements.</span></span> <span data-ttu-id="78234-118">Vissa funktionella luckor kommer troligen att ersättas med funktioner som hjälper till att uppfylla särskilda affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="78234-118">Some functional gaps will likely be replaced with features that help meet specific business requirements.</span></span> <span data-ttu-id="78234-119">Andra luckor kan emellertid fyllas genom att man fortsätter att tillåta bokföring i en journal - som när En verifikation används - men förbättrar systemet så att detta kan spåra mer detaljerat efter behov.</span><span class="sxs-lookup"><span data-stu-id="78234-119">However, other gaps might be filled by continuing to allow for entry in a journal, as when One voucher is used, but enhancing the system to track more detail as required.</span></span>

## <a name="where-can-i-track-the-progress-of-the-feature-gaps-being-filled"></a><span data-ttu-id="78234-120">Var kan jag spåra förloppet för funktionsluckor som fylls i?</span><span class="sxs-lookup"><span data-stu-id="78234-120">Where can I track the progress of the feature gaps being filled?</span></span>

<span data-ttu-id="78234-121">Precis som för varje ny funktion måste kunderna studera versionsplanen och dokumentationen "Vad är nytt eller ändrat".</span><span class="sxs-lookup"><span data-stu-id="78234-121">As for every new feature, customers must watch the Release plan and "What's new or changed" documentation.</span></span> <span data-ttu-id="78234-122">Varje funktion läggs till i dessa dokument och en anteckning indikerar att funktionen krävs för att uppfylla ett affärsbehov som tidigare krävt funktionen En verifikation.</span><span class="sxs-lookup"><span data-stu-id="78234-122">Each feature will be added to these documents, and a note will indicate that the feature is required to meet a business requirement that previously required the One voucher functionality.</span></span>

## <a name="when-the-deprecation-date-is-identified-where-will-it-be-communicated"></a><span data-ttu-id="78234-123">När avskrivningsdatum identifierats, var kommer detta att kommuniceras?</span><span class="sxs-lookup"><span data-stu-id="78234-123">When the deprecation date is identified, where will it be communicated?</span></span>

<span data-ttu-id="78234-124">Avskaffandet av En verifikation är en viktig ändring som kommuniceras allmänt.</span><span class="sxs-lookup"><span data-stu-id="78234-124">The deprecation of One voucher is a significant change that will be widely communicated.</span></span> <span data-ttu-id="78234-125">Detta kommuniceras via produktdokumentationen, ett blogginlägg och meddelanden på tillämpliga Microsoft-konferenser långt innan det datum då avvisningen börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="78234-125">It will be communicated through the product documentation, a blog post, and announcements at applicable Microsoft conferences, well in advance of the date when the deprecation takes effect.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]