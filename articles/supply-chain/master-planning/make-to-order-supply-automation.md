---
title: Tillverka mot order-automation
description: I den här artikeln beskrivs hur du ställer in och använder de olika förbättringar som har lagts till av funktionen Tillverka mot order-automation.
author: t-benebo
ms.date: 07/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-27
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9044acb472548a797ed387b08ca6892459785793
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220599"
---
# <a name="make-to-order-supply-automation"></a>Tillverka mot order-automation

[!include [banner](../includes/banner.md)]

Funktionen *Tillverka mot order-automation* lägger till flera förbättringar Microsoft Dynamics 365 Supply Chain Management. Dessa förbättringar gör att du kan utföra följande uppgifter:

- Visa resurskapacitetsbeläggningen för en användardefinierad period och aktivera därför långsiktig utvärdering av kapacitetsbeläggning.
- Förbättra flexibiliteten genom att kontrollera fördröjningstoleransen (negativa dagar) för varje huvudplan.
- Låt produkter vara tillgängliga i sista minuten och optimera användningen av befintlig leverans genom att pegging av den senast möjliga tillgången till en efterfrågan i stället för att använda första möjliga leverans.
- Håll komponenttilldelningen flexibel för tillverkningsorder efter att ha bekräftats, så att systemet kan optimera för efterfrågeändringar i sista minuten. Begränsa alltså markeringen till en nivå.
- Styr uppfyllelsepolicyn för varje försäljningsorder. Standardinställningarna tas från kundinställningarna.
- Förbättra informationsflödet mellan företag. Inköpsorder uppdateras så att de inkluderar fält för leveranssätt, leveransvillkor och externt artikelnummer. Denna ändring garanterar att detaljerad efterfrågeinformation flödar till leveransföretaget.

I denna artikel beskrivs hur du konfigurerar och använder varje förbättring.

> [!NOTE]
> Alla förbättringar som beskrivs i den här artikeln gäller för system som använder inbyggd huvudplanering. Följande två förbättringar stöds även av tillägget Planeringsoptimering för Microsoft Dynamics 365 Supply Chain Management:
>
> - Fördröjningstolerans för huvudplaner
> - Kontrollera pegging-sekvensen som används under huvudplaneringen

## <a name="turn-on-the-make-to-order-supply-automation-feature"></a>Aktivera funktionen Tillverka mot order-automation

Innan du kan använda funktionerna som beskrivs i denna artikel måste du aktivera dem i systemet. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) anges den här funktionen på följande sätt:

- **Modul:** *huvudplanering*
- **Funktionsnamn:** *Tillverka mot order-automation*

## <a name="set-the-number-of-days-to-show-on-capacity-load-page"></a>Ställ in antalet dagar som ska visas på sidan kapacitetsbeläggning

På sidan **kapacitetsbeläggning** kan du granska en resurs tillgängliga kapacitet. Funktionen *Tillverka mot order-automation* förbättrar sidan **kapacitetsbeläggning** genom att lägga till fältet **Antal dagar**. Du kan använda det här fältet för att begränsa antalet dagar som rutnätet **översikt** visar. Värdet du anger sparas i minnet. Om du lämnar sidan och sedan returnerar senare visar rutnätet **Översikt** det antal dagar som du senast angav.

Öppna sidan **kapacitetsbeläggning** så att du kan granska tillgänglig kapacitet för en enskild resurs genom att följa stegen nedan.

1. Gå till **Organisationsadministration \> Resurser \> Resurser**.
1. Välj en resurs att inspektera.
1. I åtgärdsfönstret på fliken **Resurs** i gruppen **Vy**, välj **Kapacitetsbeläggning**.
1. Använd filtret **Antal dagar** för att begränsa antalet dagar som **översikt** visar.

Öppna sidan **kapacitetsbeläggning** så att du kan granska tillgänglig kapacitet för en resursgrupp genom att följa stegen nedan.

1. Gå till **Organisationsadministration \> Resurser \> Resursgrupper**.
1. Välj en resursgrupp att inspektera.
1. I åtgärdsfönstret på fliken **Resursgrupp** i gruppen **Vy**, välj **Kapacitetsbeläggning**.
1. Använd filtret **Antal dagar** för att begränsa antalet dagar som **översikt** visar.

## <a name="apply-a-single-level-of-marking-when-you-firm-planned-orders"></a>Använd en enda nivå av markering när du bekräftar planerade order

*Märkning* används för att koppla tillgång och efterfrågan. Den påminner om *pegging*, som visar hur efter frågan förväntas täcka huvudplaneringen. Markering är dock mer permanent än pegging. Funktionen *Tillverka mot order-automation* lägger till möjligheten att begränsa lagermärkningen till en nivå när planerade beställningar fastställs. Det lägger till följande nya alternativ i fältet **Uppdatera markering** i dialogrutan **Bekräftelse** när du bekräftar en planerad order:

- *Standard på en nivå* – Markering på en nivå används. Markeringar på en nivå markerar endast huvudartikeln, inte dess strukturlistekomponenter. Därför kan du vara flexibel i komponenttilldelningen för tillverkningsorder när du har bekräftat. Med en nivåmarkering kan systemet optimera för ändringar av efterfrågan i sista minuten. I *standard* markering på en nivå markeras behovsorder mot uppfyllelseorder, men uppfyllelseorder markeras inte om de har resterande kvantitet.
- *Utökad på en nivå* – Markering på en nivå används. I *utökad* markering på en nivå markeras behovsorder mot uppfyllelseorder, men uppfyllelseorder markeras alltid oavsett om hur många som finns kvar.

De här alternativen är även tillgängliga i fältet **Uppdateringsmarkering** på fliken **Standarduppdatering** på sidan **Huvudplaneringsparametrar** page,där du definierar standardvalet för dialogrutan **Bekräftelse**.

Mer information finns i [Lagermarkeringen med Planeringsoptimering](planning-optimization/marking.md).

## <a name="set-delay-tolerance-negative-days-at-the-master-plan-level"></a>Ange fördröjningstolerans (negativa dagar) på huvudplaneringsnivå

Funktionen *Tillverka mot order-automation* lägger till möjligheten att konfigurera fördröjningstolerans (negativa dagar) på huvudplaneringsnivå. Inställningen är även tillgänglig vid artikel disponerings- och disponeringsgruppnivåerna. Om negativa dagar tilldelas på mer än en nivå används följande hierarki för att avgöra vilken inställning som ska användas:

- Om negativa dagar har konfigurerats på sidan **Huvudplaner** åsidosätter den inställningen alla andra negativa dagar när planen körs.
- Om negativa dagar har konfigurerats på sidan **Artikel disponering** åsidosätter den inställningen för disponeringsgrupp.
- Negativa dagar som konfigureras på sidan **Disponeringsgrupper** gäller bara om negativa dagar inte har konfigurerats för en relevant artikel eller huvudplan.

Ställ in negativa dagar för en huvudplan genom att följa dessa steg.

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj en huvudplan i listrutan eller skapa en ny.
1. På snabbfliken **Tidsgräns i dagar** anger du alternativet **Negativa dagar** till *Ja*.
1. I det närliggande fältet anger du antalet negativa dagar som ska tillåtas.

Mer information om hur du använder negativa dagar finns i [Fördröjningstolerans (negativa dagar)](planning-optimization/delay-tolerance.md).

## <a name="control-the-pegging-sequence-used-during-master-planning"></a>Kontrollera pegging-sekvensen som används under huvudplaneringen

I huvudplaneringen används en *pegging-sekvens* för att avgöra vilken leverans som täcker vilken efterfrågan. Funktionen *Tillverka mot order-automation* lägger till ett nytt alternativ för **Använd senast möjliga leverans** som ger dig mer kontroll över kopplingssekvensen. Det nya alternativet låter produkter vara tillgängliga i sista minuten och optimera användningen av befintlig leverans genom att pegging av den senast möjliga tillgången till en efterfrågan i stället för att använda första möjliga leverans.

Du kan ställa in pegging-sekvensen på huvudplan, artikel disponering eller disponeringsgruppnivå. Om en pegging-sekvens ställs in på mer än en nivå, används följande hierarki för att avgöra vilken inställning som ska användas:

- Om en pegging-sekvens har ställts in på sidan **Huvudplaner** åsidosätter den inställningen alla andra inställningar för pegging när planen körs.
- Om en pegging-sekvens är inställd på sidan **Artikel disponering** åsidosätter den inställningen för disponeringsgrupp.
- Pegging-sekvensen som ställs in på sidan **Disponeringsgrupper** gäller endast om inställningar för pegging-sekvens inte har konfigurerats för en relevant artikel eller huvudplan.

Om du vill ställa in pegging på disponeringsgruppnivå gör du på följande sätt.

1. Gå till **huvudplanering \> inställningar \> täckning \> disponeringsgrupper**.
1. Välj en grupp i listrutan eller skapa en ny.
1. På snabbflikarna **Allmänt** i avsnittet **Pegging-sekvens**, använd fälten **Förbruka lagerbehållning** och **Använd senaste leverans** för att konfigurera din pegging-sekvens. I registret senare i det här avsnittet visas hur de här inställningarna kombineras för att definiera pegging-sekvensen.

Om du vill ställa in pegging på artikel omfattningsnivån gör du på följande sätt.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj en produkt i rutnätet eller skapa en ny.
1. I åtgärdsfönstret, på fliken **Plan**, väljer du **Artikeldisponering**.
1. Sidan **Artikeldisponering** innehåller rader som låter dig definiera täckningsregler som gäller för artikeln på varje lager. Välj en befintlig rad i rutnätet eller skapa en ny.
1. På fliken **Allmänt**, markera kryssrutan **Åsidosätt pegging-sekvens**.
1. Använd den **Förbruka lagerbehållning** och **Använd senaste leverans** för att konfigurera din pegging-sekvens. I registret senare i det här avsnittet visas hur de här inställningarna kombineras för att definiera pegging-sekvensen.

Om du vill ställa in pegging på huvudplannivån gör du på följande sätt.

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj en huvudplan i listrutan eller skapa en ny.
1. På snabbfliken **allmänt** anger du alternativet **Åsidosätt pegging-sekvens** till *Ja*.
1. Använd den **Förbruka lagerbehållning** och **Använd senaste leverans** för att konfigurera din pegging-sekvens. I registret senare i det här avsnittet visas hur de här inställningarna kombineras för att definiera pegging-sekvensen.

Följande tabell visar hur **Förbruka lagerbehållning** och **Använd senaste leverans** kombineras för att fastställa din pegningssekvens.

| | Använd senast leverans = Ja | Använd senast leverans = Nej |
|---|---|---|
| **Förbruka lagerbehållning** = *Före all leverans* | <ol><li>Behållning</li><li>Befintlig leverans som kan uppfylla efterfrågedatumet</li><li>Befintlig leverans som inte kan uppfylla efterfrågedatumet men fortfarande inom negativa dagar</li><li>Skapa nytt leverans (planerad order)</li></ol> | <ol><li>Behållning</li><li>Befintlig leverans som kan uppfylla efterfrågedatumet</li><li>Befintlig leverans som inte kan uppfylla efterfrågedatumet men fortfarande inom negativa dagar</li><li>Skapa nytt leverans (planerad order)</li></ol> |
| **Förbruka lagerbehållning** = *Efter all leverans* | <ol><li>Befintlig leverans som kan uppfylla efterfrågedatumet</li><li>Behållning</li><li>Befintlig leverans som inte kan uppfylla efterfrågedatumet men fortfarande inom negativa dagar</li><li>Skapa nytt leverans (planerad order)</li></ol> | <ol><li>Befintlig leverans som kan uppfylla efterfrågedatumet</li><li>Befintlig leverans som inte kan uppfylla efterfrågedatumet men fortfarande inom negativa dagar</li><li>Behållning</li><li>Skapa nytt leverans (planerad order)</li></ol> |

## <a name="review-and-set-the-fulfillment-policy-that-applies-to-each-sales-order"></a>Granska och ställ in uppfyllelsepolicyn som gäller för varje försäljningsorder

Uppfyllelsepolicyer styr procentandelen av det totala orderpriset eller kvantiteten som måste reserveras fysiskt innan du kan släppa en försäljningsorder till lagret. Du kan ställa in en global standard uppfyllelsepolicy och sedan åsidosätta den för vissa kunder när det behövs. Funktionen *Tillverka mot order-automation* lägger till möjligheten att se vilken standardpolicy som faktiskt gäller för alla beställningar och tillämpa en beställningsspecifik åsidosättning efter behov.

- För att ställa in den globala uppfyllelsepolicyn som standard för försäljningsorder, gå till **Kundreskontra \> Inställning \> Parametrar för kundreskontra**. Sedan på fliken **Warehouse management** ange fältet **Uppfyllelsepolicy för försäljningsorder** till namnet på den policy som du vill använda. 
- Om du vill ange en kundspecifik uppfyllelsepolicy för försäljningsorder, gå till **Kundreskontra \> Kunder \> Alla kunder**. Sedan på fliken **Lagerställe** ange fältet **Uppfyllelsepolicy** till namnet på den policy som du vill använda.

Följ de här stegen om du vill visa standardpolicyn som gäller för en order och tillämpa en orderspecifik åsidosättning.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Öppna försäljningsordern som du vill inspektera eller redigera.
1. Markera vyer **rubrik**.
1. På snabbflikarna **Lagerställe** kan du granska och redigera följande fält efter behov:

    - **Policy för uppfyllelse av order** – Välj den uppfyllelsepolicy som ska användas för den valda ordern. Standardpolicyn åsidosätts. Om du vill använda standardpolicyn för uppfyllelse som visas i fältet **Standardvillkorspolicy** låter du det här fältet vara tomt.
    - **Standardpolicy för uppfyllelse** – I det här fältet visas den policy för standard uppfyllelse som gäller om fältet **Policy för orderuppfyllelse** är tomt. Detta fält är skrivskyddat. Om den är tom har ingen kundspecifik eller global standardpolicy för uppfyllelse definierats.

    Om både fältet **Uppfyllelsepolicy för order** och fältet **Standardpolicy för uppfyllelse** är tomma, ingen uppfyllelsepolicy gäller. Andra restriktioner kan dock finnas och kan kräva att reservationer eller andra villkor uppfylls innan försäljningsordern kan frisläppas.

## <a name="set-the-delivery-mode-and-terms-on-individual-purchase-order-lines"></a>Ange leveransläge och villkor för enskilda inköpsorderrader

Alla inköpsorder inkluderar **leveransvillkor** och **leveranssätt** i orderrubriken. Funktionen *Tillverka mot order-automation* lägger till dessa inställningar till varje orderrad. Därför kan du definiera åsidosättningar av **leveransvillkor** och/eller **leveranssätt** för alla orderrader efter behov. För rader där ingen åsidosättning har definierats används värdet från sidhuvudet. Du kan ange om värdet i ett eller båda fälten i orderrubriken också ska uppdatera alla rader.

Om du vill ange vad som ska hända med radinställningarna om en användare ändrar **leveransvillkoren** och/eller **leveranssättet** i en orderrubrik följer du dessa steg.

1. Gå till **Anskaffning och källa \> Inställningar \> Anskaffnings- och källparametrar**.
1. På fliken **Allmänt** på snabbfliken **Standardvärden och parametrar** välj länken **Uppdatera orderrader**.
1. I dialogrutan **Uppdatera orderrader** i fältet **Uppdatera leveransvillkor** och **Uppdatera leveranssätt** välj ett av följande värden:

    - *Aldrig* – Uppdatera aldrig orderraderna efter att inställningarna har ändrats i orderrubriken.
    - *Alltid* – Uppdatera alltid orderraderna efter att inställningarna har ändrats i orderrubriken.
    - *Prompt* – Om en användare ändrar en av eller båda inställningarna i orderrubriken öppnar du en dialogruta med en fråga om användaren vill uppdatera alla rader så att den matchar ändringen med en eller båda inställningarna.

Följ de här stegen om du vill ange leveransinformation i ett inköpsorderhuvud.

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Öppna inköpsordern som du vill redigera.
1. Markera vyer **rubrik**.
1. På snabbfliken **Leverans** ange **leveranssätt** och **Leveransvillkor** som önskat.
1. Beroende på inställningarna på sidan **Anskaffnings- och inköpsparametrar** kan du få frågan om du vill tillämpa ändringarna på alla orderrader.

Följ dessa steg för att ange åsidosättande av leveransinformation för en inköpsorderrad.

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Öppna inköpsordern som du vill redigera.
1. Markera vyer **Rader**.
1. I snabbfliken **Inköpsorderrader** välj raden att redigera.
1. På snabbfliken **Raddetaljer** på fliken **Leverans** ange fälten **Leveranssätt** och **Leveransvillkor** enligt önskemål. Rensa ett eller båda fälten om du vill använda matchningsinställningarna i rubriken.

För koncerninterna order synkroniseras värdena för fälten **Leveranssätt** och **Leveransvillkor** på varje inköpsorderrad mellan inköpsordern och dess relaterade försäljningsorder.

## <a name="sync-external-item-ids-and-descriptions-for-intercompany-orders"></a>Synkronisera externa artikel-ID och beskrivningar av koncerninterna order

För koncerninterna order ger funktionen *Tillverka mot order-automation* gör att externa artikel-ID:n och textbeskrivningar på inköpsorderrader kan synkroniseras med relaterade koncerninterna försäljningsorderrader, oavsett om inköpsordern är för direktleverans. Funktionen lägger också till möjligheten att ange det slutliga externa kundkontot på en koncernintern inköpsorder. I systemet hämtas externa artikel-/textbeskrivningar automatiskt från den externa kundposten i stället för posten för den (interna) koncerninterna leverantören.

Ställ in en koncernintern leverantör så att externa artikel- och artikelnamn synkroniseras mellan koncerninterna inköpsorder och relaterade koncerninterna försäljningsorder genom att följa stegen nedan.

1. Gå till **Anskaffning och källa \> Leverantörer \> Alla leverantörer**.
1. Välj den koncerninterna leverantör som du vill konfigurera.
1. I åtgärdsfönstret, på fliken **Allmänt**, i gruppen **Ställ in**, klicka på **Koncernintern**.
1. På sidan **koncernintern** på fliken **Policyer för inköpsorder** i avsnittet **Koncernintern inköpsorder -\> Koncernintern försäljningsorder** markera kryssrutan **Externt artikel-ID och artikelnamn**.

Följ dessa steg för att ange det slutliga externa kundkontot för en inköpsorder mellan företag. Fältet **Kundkonto** gäller endast för koncerninterna inköpsorder. Använd det för att ange kontonumret för den kund som så småningom kommer att ta emot varorna. När det här fältet är inställt kommer inköpsorderrader att ta externa artikelbeskrivningar och nummer från det angivna kundkontot i stället för den koncerninterna leverantör som angetts på inköpsordern. Om du ändrar kundkontot senare kommer externa artikelbeskrivningar och ID:n att uppdateras så att de matchar värdena för det nya kontot. Externa artikelbeskrivningar och ID för varje rad synkroniseras också med den matchande koncerninterna försäljningsordern.

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Öppna den inköpsorder som du vill skapa eller skapa en ny.
1. Markera vyer **rubrik**.
1. I avsnittet **Referens** ange fältet **Kundkonto** till relevant externt kundkonto.

Följ de här stegen om du vill ange externa artikel-/textbeskrivningar för en inköpsorderrad för en koncernintern order. Värdena du anger synkroniseras med de relaterade koncerninterna försäljningsorderraderna, oavsett om inköpsordern gäller för direktleverans eller inte.

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Öppna den inköpsorder som du vill skapa eller skapa en ny.
1. Markera vyer **Rader**.
1. I snabbfliken **Inköpsorderrader** välj raden att redigera.
1. På snabbfliken **Raddetaljer** på fliken **Allmänt** i avsnittet **Orderrad** i fältet **Text** ge en extern beskrivning av artikeln som anges på den valda orderraden. Det här värdet synkroniseras med den relaterade koncerninterna försäljningsorderraden.
1. I avsnittet **Referens** i fältet **Extern** ange ett externt artikel-ID för artikeln som anges på den valda orderraden. Det här värdet synkroniseras med den relaterade koncerninterna försäljningsorderraden.

För mer information, se [Skapa och fakturera en koncernintern försäljningsorder för en extern kund](../sales-marketing/intercompany-sales-order-for-external-customer.md).
