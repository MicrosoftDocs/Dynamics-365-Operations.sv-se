---
title: Förfrågningar om hemtagningskostnad
description: I det här avsnittet beskrivs hur du söker efter och använder de olika typer av förfrågningar som är tillgängliga för modulen hemtagningskostnad.
author: sherry-zheng
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMLine, ITMItemTracking, ITMContainerActivityTracking, ITMContainerTracking
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 22a2e76780adb43b053b6cf7fd08411a4a60aeac
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823371"
---
# <a name="landed-cost-inquiries"></a>Förfrågningar om hemtagningskostnad

[!include [banner](../../includes/banner.md)]

## <a name="voyage-line-inquiries"></a>Förfrågningar om färdrad

Förfrågan om **färdrader** visar alla färdrader när det gäller inventering. Denna förfrågan kan användas som ett filter för att hjälpa dig att hitta en artikel, inköpsorder eller annan användbar information. Den kan också användas för att identifiera förväntat leveransdatum för en artikel som kan finnas på en eller flera färder. På det här sättet kan det hjälpa dig att hantera förväntad lagerinleverans.

Om du vill öppna denna förfrågan går du till **Hemtagningskostnad \> Förfrågningar \> Färdrader**.

### <a name="overview-tab"></a>Fliken Översikt

På fliken **Översikt** på förfrågningssidan **Färdrader** finns ett rutnät som visar grundläggande information om varje relevant färdrad. Följande tabell beskriver kolumnerna i rutnätet.

| Kolumn | beskrivning |
|---|---|
| **Artikelnummer** | Artikeln för färdraden. |
| **Referens** | Ordertypen (inköpsorder eller överföringsorder). |
| **Antal** | Inköpsordernummer eller överföringsordernummer. |
| **Folio** | Den folio som är associerad med färdraden. |
| **Fraktcontainer** | Den leveransbehållare som är associerad med färdraden. |
| **Sjötransport** | Den färd som är associerad med färdraden. |
| **Kvantitet** | Kvantiteten av artiklar för färdraden. |
| (Övriga dimensioner) | Du kan visa kolumner för ytterligare dimensioner om det behövs. Dimensionerna inkluderar batchnummer, lagerstatus och lagerställe. I åtgärdsfönstret, välj **Lager \> Visa dimensioner** om du vill öppna en dialogruta där du kan välja vilka dimensioner som ska ingå. |

### <a name="general-tab"></a>Fliken Allmänt

Välj fliken **Allmänt** om du vill visa mer information om raden som har valts på fliken **Översikt**.

### <a name="dimensions-tab"></a>Fliken Dimensioner

Välj fliken **Dimensioner** för att visa värden för alla tillgängliga dimensioner för den rad som för närvarande har markerats på fliken **Översikt**, oavsett vilka dimensioner du har valt att visa på den fliken.

## <a name="cost-estimate-inquiries"></a>Kostnadsuppskattning förfrågningar

Varje gång du genererar en kostnadsuppskattning läggs uppskattningen till på sidan **Kostnadsuppskattningar**. Detaljerad information om hur du genererar, visar och arbetar med kostnadsuppskattningar (inklusive uppskattningar på förfrågan), finns i [Uppskattning och hantering av hemtagningskostnader](estimate-manage-landed-costs.md).

## <a name="item-tracking"></a>Artikelspårning

Använd sidan **Artikelspårning** kan du visa öppna inköpsorderrader och deras aktuella status. Rader behöver inte kopplas till en sådan för att kunna visas här. Om en artikel är kopplad till en rad, visar artikelspårningspostraden emellertid färd-ID.

Om du vill öppna den här sidan går du **Hemtagningskostnad \> Förfrågningar \> Spårning \> Artikelspårning**.

Eftersom systemet troligen innehåller ett mycket stort antal inköpsorderrader visas inga poster på sidan **artikelspårning**. Börja med att använda filterfälten överst på sidan för att definiera den uppsättning inköpsorderrader som du vill ha. Välj sedan **Uppdatera** i åtgärdsfönstret för att generera listan. Du kan använda en asterisk (\*) som jokertecken i något av filterfälten. Om du till exempel vill söka efter alla inköpsorderrader för artiklar som innehåller ordet "DVD" i namnet ställer du in fältet **Typ** till **Produknamn** och anger *\*DVD\** i fältet **Fältvärde**.

> [!NOTE]
> Restorder omfattar för närvarande endast försäljningsorder. Försäljningsofferter visas eller betraktas inte som restorder.

I följande tabell beskrivs kolumnerna i rutnätet på sidan **Artikelspårning**.

| Kolumn | beskrivning |
|---|---|
| **Till hamn** | Slutdestinationen. |
| **Bekräftat** | Bekräftat datum för inköpsordern. |
| **Leveransdatum** | Leveransdatum för inköpsordern. |
| **Sjötransport** | Om raden är associerad med en färd, färd-ID. |
| **Leveransbehållare** | Om raden är kopplad till en leveransbehållare, behållar-ID. |
| **Leveranshamn** | Den aktuella porten, baserat på det första steget i spårningsformuläret där inget faktiskt datum har angetts för den skeppningsbehållare som är associerad med inköpsorderraden. |
| **Aktivitet** | Den aktuella aktivitet, baserat på det första steget i spårningsformuläret där inget faktiskt datum har angetts för den skeppningsbehållare som är associerad med inköpsorderraden. |
| **Uppskattat slutdatum** | Det datum då färden förväntas inlevereras till lagerstället vid destinationen. |
| **Namn** | Namn på leverantören. |
| **Färdstatus** | Leveransstatusen som bifogas inköpsordern. |
| **Artikelnummer** | Artikelnumret för inköpsorderraden. |
| **Externt** | Leverantörens artikelnamn. |
| **Produktnamn** | Namn på artikeln för inköpsorderraden. |
| **Kvantitet** | Inköpsorderradens kvantitet för inköpsorderraden. |
| **Enhet** | Måttenheten för inköpsorderraden. |
| **Referens** | Ordertypen (inköpsorder eller överföringsorder) |
| **Referensnummer** | Inköpsordernummer eller överföringsordernummer. |
| **Restorder** | En symbol indikerar att det finns försäljnings restorder för artikeln. |
| (Övriga dimensioner) | Du kan visa kolumner för ytterligare dimensioner om det behövs. Dimensionerna inkluderar batchnummer, lagerstatus och lagerställe. I åtgärdsfönstret, välj **Visa dimensioner** om du vill öppna en dialogruta där du kan välja vilka dimensioner som ska ingå. |

### <a name="related-information-about-backorders"></a>Relaterad information om restorder

Om du vill visa mer information om restorder markerar du fliken **Relaterad information** till höger på sidan och väljer **Restorder**. Om du vill visa ännu mer information om en viss restorder markerar du raden för den och väljer sedan länken **Mer**.

## <a name="individual-shipping-container-tracking"></a>Spårning av enskild fraktcontainer

I förfrågan om **individuell spårning av leveransbehållare** finns ett filter som gör att du kan hitta en leveransbehållare och sedan identifiera alla rader i den behållaren.

Om du vill öppna den här förfrågan går du **Hemtagningskostnad \> Förfrågningar \> Spårning \> individuell spårning av leveransbehållare**.

## <a name="multiple-shipping-container-tracking"></a>Spårning av flera fraktcontainrar

I förfrågan om **flera spårning av leveransbehållare** finns ett filter som gör att du kan hitta en samling leveransbehållare och sedan identifiera alla rader i de behållarna.

Om du vill öppna den här förfrågan går du **Hemtagningskostnad \> Förfrågningar \> Spårning \> flera spårning av leveransbehållare**.
