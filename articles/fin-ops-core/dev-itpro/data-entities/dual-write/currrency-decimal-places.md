---
title: Migrering av valutatyp för dubbelriktad skrivning
description: I det här avsnittet beskrivs hur du ändrar antalet decimaler som stöds av dubbelriktad skrivning för valuta.
author: RamaKrishnamoorthy
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: c4f663ae36f7d4ea3db9888e618f2fe3bf8c3256
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748957"
---
# <a name="currency-data-type-migration-for-dual-write"></a><span data-ttu-id="54184-103">Migrering av valutatyp för dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="54184-103">Currency data-type migration for dual-write</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="54184-104">Du kan öka antalet decimaler som stöds för valutavärden till maximalt 10.</span><span class="sxs-lookup"><span data-stu-id="54184-104">You can increase the number of decimal places that are supported for currency values to a maximum of 10.</span></span> <span data-ttu-id="54184-105">Standardgränsen är fyra decimaler.</span><span class="sxs-lookup"><span data-stu-id="54184-105">The default limit is four decimal places.</span></span> <span data-ttu-id="54184-106">Genom att öka antalet decimaler bidrar du till att undvika dataförlust när du använder dubbelriktad skrivning för att synkronisera data.</span><span class="sxs-lookup"><span data-stu-id="54184-106">By increasing the number of decimal places, you help prevent data loss when you use dual-write to sync data.</span></span> <span data-ttu-id="54184-107">Ökningen av antalet decimaler är att välja en ändring.</span><span class="sxs-lookup"><span data-stu-id="54184-107">The increase in the number of decimal places is an opt-in change.</span></span> <span data-ttu-id="54184-108">Om du vill implementera den måste du begära hjälp från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54184-108">To implement it, you must request assistance from Microsoft.</span></span>

<span data-ttu-id="54184-109">Det finns två steg i processen att ändra antalet decimaler:</span><span class="sxs-lookup"><span data-stu-id="54184-109">The process of changing the number of decimal places has two steps:</span></span>

1. <span data-ttu-id="54184-110">Begär migrering från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54184-110">Request migration from Microsoft.</span></span>
2. <span data-ttu-id="54184-111">Ange antalet decimalplatser i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54184-111">Change the number of decimal places in Dataverse.</span></span>

<span data-ttu-id="54184-112">Finance and Operations-appen och Dataverse måste stödja samma antal decimaler i valutavärden.</span><span class="sxs-lookup"><span data-stu-id="54184-112">The Finance and Operations app and Dataverse must support the same number of decimal places in currency values.</span></span> <span data-ttu-id="54184-113">I annat fall kan det hända att data går förlorade när den här informationen synkroniseras mellan appar.</span><span class="sxs-lookup"><span data-stu-id="54184-113">Otherwise, data loss can occur when this information is synced between apps.</span></span> <span data-ttu-id="54184-114">Vid migreringsprocessen omkonfigureras det sätt på vilket valuta- och växelkursvärden lagras, men inga data ändras.</span><span class="sxs-lookup"><span data-stu-id="54184-114">The migration process reconfigures the way that currency and exchange rate values are stored, but it doesn't change any data.</span></span> <span data-ttu-id="54184-115">När migreringen är slutförd kan antalet decimaler för valutakoder och priser ökas och de data som användarna anger och visar kan ha mer decimal precision.</span><span class="sxs-lookup"><span data-stu-id="54184-115">After the migration is completed, the number of decimal places for currency codes and pricing can be increased, and the data that users enter and view can have more decimal precision.</span></span>

<span data-ttu-id="54184-116">Migrering är valfritt.</span><span class="sxs-lookup"><span data-stu-id="54184-116">Migration is optional.</span></span> <span data-ttu-id="54184-117">Om du kan ha nytta av stödet för fler decimaler rekommenderar vi att du tar över migreringen.</span><span class="sxs-lookup"><span data-stu-id="54184-117">If you might benefit from support for more decimal places, we recommend that you consider migration.</span></span> <span data-ttu-id="54184-118">Organisationer som inte kräver värden med fler än fyra decimalplatser behöver inte migreras.</span><span class="sxs-lookup"><span data-stu-id="54184-118">Organizations that don't require values that have more than four decimal places don't have to migrate.</span></span>

## <a name="requesting-migration-from-microsoft"></a><span data-ttu-id="54184-119">Begär migrering från Microsoft</span><span class="sxs-lookup"><span data-stu-id="54184-119">Requesting migration from Microsoft</span></span>

<span data-ttu-id="54184-120">Lagring för befintliga valuta kolumner i Dataverse kan inte hantera fler än fyra decimaler.</span><span class="sxs-lookup"><span data-stu-id="54184-120">Storage for existing currency columns in Dataverse can't support more than four decimal places.</span></span> <span data-ttu-id="54184-121">Under migreringsprocessen kopieras därför valutavärden till nya interna kolumner i databasen.</span><span class="sxs-lookup"><span data-stu-id="54184-121">Therefore, during the migration process, currency values are copied to new internal columns in the database.</span></span> <span data-ttu-id="54184-122">Den här processen sker kontinuerligt tills alla data har migrerats.</span><span class="sxs-lookup"><span data-stu-id="54184-122">This process occurs continuously until all data has been migrated.</span></span> <span data-ttu-id="54184-123">Vid slutet av migreringen ersätter de nya lagringstyperna de gamla lagringstyperna, men datavärdena ändras inte.</span><span class="sxs-lookup"><span data-stu-id="54184-123">Internally, at the end of migration, the new storage types replace the old storage types, but the data values are unchanged.</span></span> <span data-ttu-id="54184-124">Valutakolumner kan sedan stödja upp till 10 decimaler.</span><span class="sxs-lookup"><span data-stu-id="54184-124">The currency columns can then support up to 10 decimal places.</span></span> <span data-ttu-id="54184-125">Under migreringsprocessen kan Dataverse fortfarande användas utan avbrott.</span><span class="sxs-lookup"><span data-stu-id="54184-125">During the migration process, Dataverse can continue to be used without interruption.</span></span>

<span data-ttu-id="54184-126">På samma gång ändras valutakurserna så att de stöder upp till 12 decimaler i stället för den aktuella gränsen på 10.</span><span class="sxs-lookup"><span data-stu-id="54184-126">At the same time, exchange rates are modified so that they support up to 12 decimal places instead of the current limit of 10.</span></span> <span data-ttu-id="54184-127">Den här ändringen krävs för att antalet decimaler ska vara samma i både Finance and Operations-appen och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54184-127">This change is required so that the number of decimal places is the same in both the Finance and Operations app and Dataverse.</span></span>

<span data-ttu-id="54184-128">Migreringen ändrar inte några data.</span><span class="sxs-lookup"><span data-stu-id="54184-128">Migration doesn't change any data.</span></span> <span data-ttu-id="54184-129">När du har konverterat kolumnerna valuta och valutakurs kan administratörer konfigurera systemet att använda upp till 10 decimaler för valutakolumner genom att ange antalet decimaler för varje transaktionsvaluta och för prissättning.</span><span class="sxs-lookup"><span data-stu-id="54184-129">After the currency and exchange rate columns are converted, admins can configure the system to use up to 10 decimal places for currency columns by specifying the number of decimal places for each transaction currency and for pricing.</span></span>

### <a name="request-a-migration"></a><span data-ttu-id="54184-130">Begär en migrering</span><span class="sxs-lookup"><span data-stu-id="54184-130">Request a migration</span></span>

<span data-ttu-id="54184-131">Gör den här funktionen tillgänglig genom att använda e-post **CDSExpandDecimal@microsoft.com** och inkludera följande information:</span><span class="sxs-lookup"><span data-stu-id="54184-131">To make this feature available, email **CDSExpandDecimal@microsoft.com**, and include the following information:</span></span>

+ <span data-ttu-id="54184-132">**Ämne:** begäran om att aktivera expanderat decimalstöd för \<organizationID\></span><span class="sxs-lookup"><span data-stu-id="54184-132">**Subject:** Request to enable expanded decimal support for \<organizationID\></span></span>
+ <span data-ttu-id="54184-133">**Brödtext:** Jag vill aktivera expanderat decimalstöd för min organisation \<organizationID\>.</span><span class="sxs-lookup"><span data-stu-id="54184-133">**Body:** I would like to enable expanded decimal support for my org \<organizationID\>.</span></span>

<span data-ttu-id="54184-134">En Microsoft-representant kommer att kontakta dig inom två till tre arbetsdagar under de kommande stegen.</span><span class="sxs-lookup"><span data-stu-id="54184-134">A Microsoft representative will contact you within two to three business days for the next steps.</span></span>

<span data-ttu-id="54184-135">När du begär en migrering bör du vara medveten om följande uppgifter och planera för dem i enlighet med detta:</span><span class="sxs-lookup"><span data-stu-id="54184-135">When you request a migration, you should be aware of the following details and plan for them accordingly:</span></span>

+ <span data-ttu-id="54184-136">Den tid som krävs för att migrera data beror på mängden data i systemet.</span><span class="sxs-lookup"><span data-stu-id="54184-136">The time that is required to migrate the data depends the amount of data in the system.</span></span> <span data-ttu-id="54184-137">Migrering av stora databaser kan ta flera dagar.</span><span class="sxs-lookup"><span data-stu-id="54184-137">Migration of large databases can take several days.</span></span>
+ <span data-ttu-id="54184-138">Databasens storlek ökar tillfälligt när migreringen körs, eftersom det krävs ytterligare utrymme för index.</span><span class="sxs-lookup"><span data-stu-id="54184-138">The size of the database temporarily increases while the migration is running, because additional space is needed for indexes.</span></span> <span data-ttu-id="54184-139">Större delen av det extra utrymmet frigörs när migreringen är slutförd.</span><span class="sxs-lookup"><span data-stu-id="54184-139">Most of the additional space is freed when the migration is completed.</span></span>
+ <span data-ttu-id="54184-140">Om fel uppstår under migreringsprocessen när migreringen inte kan slutföras, höjer systemet notifieringar till Microsoft-supporten så att supportpersonalen kan ingripa.</span><span class="sxs-lookup"><span data-stu-id="54184-140">During the migration process, if errors occur that prevent the migration from being completed, the system raise alerts to Microsoft Support, so that Support staff can intervene.</span></span> <span data-ttu-id="54184-141">Även om fel uppstår under migreringen förblir Dataverse helt tillgänglig för regelbunden användning.</span><span class="sxs-lookup"><span data-stu-id="54184-141">However, even if errors occur during the migration, Dataverse remains fully available for regular use.</span></span>
+ <span data-ttu-id="54184-142">Migreringsprocessen går inte att ångra.</span><span class="sxs-lookup"><span data-stu-id="54184-142">The migration process isn't reversible.</span></span>

## <a name="changing-the-number-of-decimal-places"></a><span data-ttu-id="54184-143">Ändra antalet decimaler</span><span class="sxs-lookup"><span data-stu-id="54184-143">Changing the number of decimal places</span></span>

<span data-ttu-id="54184-144">När migreringen har slutförts kan Dataverse lagra nummer med fler decimaler.</span><span class="sxs-lookup"><span data-stu-id="54184-144">After the migration is completed, Dataverse can store numbers that have more decimal places.</span></span> <span data-ttu-id="54184-145">Administratörer kan välja hur många decimaler som ska användas för särskilda valutakoder och för prissättning.</span><span class="sxs-lookup"><span data-stu-id="54184-145">Admins can choose how many decimal places are used for specific currency codes and for pricing.</span></span> <span data-ttu-id="54184-146">Användare av Microsoft Power Apps, Power BI och Power Automate kan sedan visa och använda tal med fler decimaler.</span><span class="sxs-lookup"><span data-stu-id="54184-146">Users of Microsoft Power Apps, Power BI, and Power Automate can then view and use numbers that have more decimal places.</span></span>

<span data-ttu-id="54184-147">Om du vill göra den här ändringen måste du uppdatera följande inställningar i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="54184-147">To make this change, you must update the following settings in Power Apps:</span></span>

+ <span data-ttu-id="54184-148">**Systeminställningar: valutaprecision för prissättning** – Kolumnen **ange valutaprecisionen som används för prissättning i hela system** anger hur valutan ska uppföras för organisationen när **Prissättningsprecision** är vald.</span><span class="sxs-lookup"><span data-stu-id="54184-148">**System Settings: Currency precision for pricing** – The **Set the currency precision that is used for pricing throughout the system** column defines how the currency will behave for the organization when **Pricing Precision** is selected.</span></span>
+ <span data-ttu-id="54184-149">**Företagshantering: valutor** – Kolumnen **Valutaprecision** låter dig ange ett anpassat antal decimaler för en viss valuta.</span><span class="sxs-lookup"><span data-stu-id="54184-149">**Business Management: Currencies** – The **Currency Precision** column lets you specify a custom number of decimal places for a specific currency.</span></span> <span data-ttu-id="54184-150">Det finns en återgång till inställningen för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="54184-150">There is a fallback to the organization-wide setting.</span></span>

<span data-ttu-id="54184-151">Det finns några begränsningar:</span><span class="sxs-lookup"><span data-stu-id="54184-151">There are some limitations:</span></span>

+ <span data-ttu-id="54184-152">Du kan inte konfigurera valutakolumnen i en tabell.</span><span class="sxs-lookup"><span data-stu-id="54184-152">You can't configure the currency column on a table.</span></span>
+ <span data-ttu-id="54184-153">Du kan bara ange fler än fyra decimaler på nivåerna för **Prissättning** och **Transaktionsvaluta**.</span><span class="sxs-lookup"><span data-stu-id="54184-153">You can specify more than four decimal places only at the **Pricing** and **Transaction Currency** levels.</span></span>

### <a name="system-settings-currency-precision-for-pricing"></a><span data-ttu-id="54184-154">Systeminställningar: valutaprecision för prissättning</span><span class="sxs-lookup"><span data-stu-id="54184-154">System Settings: Currency precision for pricing</span></span>

<span data-ttu-id="54184-155">När migreringen har slutförts kan administratörer ställa in valutaprecision.</span><span class="sxs-lookup"><span data-stu-id="54184-155">After migration is completed, admins can set the currency precision.</span></span> <span data-ttu-id="54184-156">Gå till **Inställningar \> Administration** och välj **Systeminställningar**.</span><span class="sxs-lookup"><span data-stu-id="54184-156">Go to **Settings \> Administration**, and select **System Settings**.</span></span> <span data-ttu-id="54184-157">På fliken **Allmänt** ändrar du värdet för kolumnen **Ange valuta precisionen som används för prissättning i hela system** som du ser i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="54184-157">Then, on the **General** tab, change the value of the **Set the currency precision that is used for pricing throughout the system** column, as shown in the following illustration.</span></span>

![Systeminställningar för valuta](media/currency-system-settings.png)

### <a name="business-management-currencies"></a><span data-ttu-id="54184-159">Affärshantering: valutor</span><span class="sxs-lookup"><span data-stu-id="54184-159">Business Management: Currencies</span></span>

<span data-ttu-id="54184-160">Om du kräver att valutaprecisionen för en viss valuta avviker från den valutaprecision som används för prissättningen kan du ändra den.</span><span class="sxs-lookup"><span data-stu-id="54184-160">If you require that the currency precision for a specific currency differ from the currency precision that is used for pricing, you can change it.</span></span> <span data-ttu-id="54184-161">Gå till **Inställningar \> Företagshantering**, välj **Valutor** och välj sedan vilken valuta du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="54184-161">Go to **Settings \> Business Management**, select **Currencies**, and select the currency to change.</span></span> <span data-ttu-id="54184-162">Ställ sedan in kolumnen **Valutaprecision** till önskat antal decimaler, som du ser i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="54184-162">Then set the **Currency Precision** column to the number of decimal places that you want, as shown in the following illustration.</span></span>

![Valutainställningar för ett specifikt språk](media/specific-currency.png)

### <a name="tables-currency-column"></a><span data-ttu-id="54184-164">tabeller: valutakolumn</span><span class="sxs-lookup"><span data-stu-id="54184-164">tables: Currency column</span></span>

<span data-ttu-id="54184-165">Antalet decimaler som kan konfigureras för särskilda valutakolumner är begränsat till fyra.</span><span class="sxs-lookup"><span data-stu-id="54184-165">The number of decimal places that can be configured for specific currency columns is limited to four.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]