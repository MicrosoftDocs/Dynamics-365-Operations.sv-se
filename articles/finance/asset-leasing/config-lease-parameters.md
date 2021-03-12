---
title: Konfigurera leasingparametrar (förhandsversion)
description: I det här ämnet beskrivs konfigurationsinställningarna för Leasing av tillgångar , t.ex. säkerhetsinformation och redovisningsinställningar.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ff0aa5fd0b78814dfa5bb00d6d5ef2984c566d14
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971413"
---
# <a name="configure-lease-parameters"></a><span data-ttu-id="79e72-103">Konfigurera leasingparametrar</span><span class="sxs-lookup"><span data-stu-id="79e72-103">Configure lease parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="79e72-104">Flera konfigurationsinställningar påverkar hur Leasing av tillgångar uppträder.</span><span class="sxs-lookup"><span data-stu-id="79e72-104">Several configuration settings affect how Asset leasing behaves.</span></span> <span data-ttu-id="79e72-105">Dessa inställningar omfattar journalnamn, allmänna parametrar och inställningar för bokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="79e72-105">These settings include journal names, general parameters, and posting profile settings.</span></span>

1. <span data-ttu-id="79e72-106">Gå till **Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**.</span><span class="sxs-lookup"><span data-stu-id="79e72-106">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="79e72-107">Välj fliken **Allmänt** på fliken **Leasing**.</span><span class="sxs-lookup"><span data-stu-id="79e72-107">On the **Leases** tab, select the **General** FastTab.</span></span>

    <span data-ttu-id="79e72-108">Parametern **Tillåt manuell åsidosättning av klassificering** avgör om leasingklassificeringen kan åsidosättas innan betalningsplanen bekräftas.</span><span class="sxs-lookup"><span data-stu-id="79e72-108">The **Allow manual classification override** parameter determines whether the lease classification can be overridden before the payment schedule is confirmed.</span></span>

    <span data-ttu-id="79e72-109">Parametern **Korsentitetsbatch** avgör om du kan bokföra till andra juridiska personer från den aktuella juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="79e72-109">The **Cross-entity batch** parameter determines whether you can post to other legal entities from the current legal entity.</span></span> <span data-ttu-id="79e72-110">Om den här parametern är aktiverad kan du skapa journalposter för de juridiska personer som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="79e72-110">If this parameter is turned on, you can create journal entries for the legal entities that you have access to.</span></span>

3. <span data-ttu-id="79e72-111">Ställ in alternativet **Tillåt borttagning av bekräftad leasing** till **Ja** om du vill tillåta att leasingar som har bekräftade betalningsplaner raderas.</span><span class="sxs-lookup"><span data-stu-id="79e72-111">Set the **Allow delete of confirmed leases** option to **Yes** to allow leases that have confirmed payment schedules to be deleted.</span></span> <span data-ttu-id="79e72-112">Leasingar kan inte tas bort om bokförda eller ej bokförda transaktioner är kopplade till dem, oavsett inställningen för detta alternativ.</span><span class="sxs-lookup"><span data-stu-id="79e72-112">Leases can't be deleted if posted or unposted transactions are associated with them, regardless of the setting of this option.</span></span> <span data-ttu-id="79e72-113">Du kan inte återställa en leasingpost när den har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="79e72-113">You can't restore a lease record after it's deleted.</span></span> <span data-ttu-id="79e72-114">Om du laddar upp poster för ett borttaget lån, antingen manuellt eller via dataentiteter, behandlas den uppladdade informationen som ny, inte som en uppdatering av en befintlig leasing.</span><span class="sxs-lookup"><span data-stu-id="79e72-114">If you upload any records for a deleted lease, either manually or through data entities, the uploaded information is treated as new, not as an update to an existing lease.</span></span>

    <span data-ttu-id="79e72-115">Om du ställer in det här alternativet på **Ja**, och övergångstypen för boken är **Kumulativt catchup-alternativ A eller B**, ställer systemet in fältet **Marginell låneränta** till värdet i fältet **Marginell låneränta vid övergång** på sidan **Bokinställning**.</span><span class="sxs-lookup"><span data-stu-id="79e72-115">If you set this option to **Yes**, and the transition type of the book is **Cumulative Catchup Option A or B**, the system sets the **Incremental borrowing rate** field to the value of the **Incremental borrowing rate at transition** field on the **Book setup** page.</span></span> <span data-ttu-id="79e72-116">Om detta alternativ är inställt på **Nej**, ställs satsen i leasinghuvudet in på värdet för fältet **Marginell låneränta** på sidan **Information om bok**, oavsett övergångstypen för boken.</span><span class="sxs-lookup"><span data-stu-id="79e72-116">If this option is set to **No**, the rate on the head lease is set to the value of the **Incremental borrowing rate** field on the **Book details** page, regardless of the transition type of the book.</span></span>

4. <span data-ttu-id="79e72-117">Ställ in alternativet **Tillåt återföringar av avskrivningar på stängd bokversion** till **Ja** för att göra så att avskrivningsutgiftstransaktioner kan återföras.</span><span class="sxs-lookup"><span data-stu-id="79e72-117">Set the **Allow depreciation reversals on closed book version** option to **Yes** to allow depreciation expense transactions to be reversed.</span></span> <span data-ttu-id="79e72-118">Utgiftstransaktioner kan återföras även om bokversionen är stängd.</span><span class="sxs-lookup"><span data-stu-id="79e72-118">Expense transactions can be reversed even when the book version is closed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79e72-119">Vi rekommenderar att du behåller detta alternativ angivet till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="79e72-119">We recommend that you keep this option set to **No**.</span></span> <span data-ttu-id="79e72-120">Inställningen för det här alternativet används som en validering och kontroll för att förhindra att en stängd boks version avskrivs av misstag.</span><span class="sxs-lookup"><span data-stu-id="79e72-120">The setting of this option is used as a validation and control to prevent a closed book version from being accidently depreciated.</span></span> <span data-ttu-id="79e72-121">Genom att välja **Nej** kan du hålla det bokförda nettovärdet och framtida avskrivningsberäkningar korrekta.</span><span class="sxs-lookup"><span data-stu-id="79e72-121">By keeping the option set to **No**, you help keep the net book value and future depreciation calculations accurate.</span></span>
