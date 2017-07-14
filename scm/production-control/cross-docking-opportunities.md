---
title: "Direktleverans från produktionsorder till utlastningsplatser | Microsoft Docs"
description: "Det här avsnittet beskriver hur du hanterar processen för direktutleveransmaterial som rapporteras som färdiga från en produktionsrad till en plats med utgående transporter."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.reviewer: bis
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 0b5541b6752da0c73e4309951ecabc0793f24289
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017

---

# Direktleverans från produktionsorder till utlastningsplatser
<a id="cross-docking-from-production-orders-to-outbound-docks" class="xliff"></a>

Det här avsnittet beskriver hur du hanterar processen för direktutleveransmaterial som rapporteras som färdiga från en produktionsrad till en plats med utgående transporter.

Introduktion
<a id="introduction" class="xliff"></a>
------------

Direktutleverans från produktion till en utlastningsplats gäller tillverkare som producerar stora volymer och vi vill skicka de färdiga produkterna när de rapporteras som färdiga från produktionsraderna. Syftet är att leverera produkter till distributionscenter som fysiskt finns nära kundefterfrågan, i stället för att bygga upp lagret på tillverkningsplatsen.

Om det inte finns några omedelbara behov för en produkt, måste det föras in till lagerställen på tillverkningsplatsen. Denna process kallas också *opportunistisk direktutleverans*, vilket innebär att om det finns ett krav på att produkten levereras, ska affärsmöjligheten användas i stället för att föra in produkten för intern lagring.

I följande exempel visas tre varianter av ett flöde som påbörjas vid slutet av produktionsrad (2).

En produkt har rapporterats som färdig för produktionsutleveransplatsen (3) och en truckförare hämtar lastpallen på den här platsen (3).

-   Om en planerad aktivitet (6) för överföring av produkten från tillverking (1) till ett distributionscenter (7), dirigeras sedan truckföraren till systemet för att placera lastpallen efter en vikdörrplats (4).
-   Om en släpvagn redan tilldelats vikdörren dirigeras truckföraren till att lasta produkten direkt till släpfordonet.
-   Om det inte sker planerad aktivitet för överföring av produkten, dirigeras truckföraren till att ställa undan produkten till en plats i det interna lagerstället (5).

[![](./media/scenario1.png)](./media/scenario1.png)

## Konfigurera direktleverans
<a id="configure-cross-docking" class="xliff"></a>
Du konfigurerar direktutleveransprocessen i **arbetspolicyer**. En arbetspolicy omfattar en arbetsordertyp, plats och produkt. I följande exempel konfigureras direktutleverans för produkt X och plats Y.

#### Typer av arbetsorder
<a id="work-order-types" class="xliff"></a>

-   Arbetsordertyp: Plats för slutförda varor
-   Metod för att skapa arbete: direktutleverans
-   Direktleveranspolicynamn: överföra order

#### Lagerplatser
<a id="inventory-locations" class="xliff"></a>

-   Lagerställe: 51
-   Plats: Y

#### Produkter
<a id="products" class="xliff"></a>

-   Artikelnummer: X

Direktutleveranser kan för närvarande konfigureras för två arbetsordertyper:

-   Plats för slutförda varor
-   Plats för samprodukt och biprodukt

I **direktutleveranspolicy** definierar du vilka dokumenttyper som är tillämpliga för direktutleverans. För närvarande är den enda dokumenttypen som stöds **överföringsorder**. Följande exempel visar konfigurationen av en direktutleveranspolicy.

### Direktleveranspolicynamn: överföringsorder
<a id="cross-docking-policy-name-transfer-order" class="xliff"></a>

-   Löpnummer: 10
-   Typ av arbetsorder: Överför leverans
-   Direktleverans kräver plats : Falskt
-   Direktutleveransstrategi: datum och tid

### Löpnummer
<a id="sequence-number" class="xliff"></a>

**Löpnumret** anger prioriteten för dokumenttypen. För närvarande är den enda dokumenttypen som stöds **överföringsorder**. Lönumret blir därför endast relevant när fler arbetsordertyper stöds.

### Direktleveranspolicy
<a id="cross-docking-policy" class="xliff"></a>

Direktutleveranspolicyn anger också policyn för prioritering av överföringsorderkrav. Om t.ex. flera överföringsorder finns för samma produkt, kommer planerat datum och tid som är inställd på lasten och associerad med överföringsordern avgör prioriteringen mellan order. Tidsplanerat datum och tid kan anges direkt på lasten eller kan ställas in på ett **mötesschema** som associeras med lasten. Prioriteringen bestäms av strategin för direktutleverans. För närvarande finns endast en metod: **datum och tid**.

### Direktleverans kräver plats
<a id="cross-docking-demand-requires-location" class="xliff"></a>

I direktutleveranspolicyn som du kan ställa in villkor för kräver att överföringsorder har en tilldelad plats för att berättiga för direktutleverans. Detta kriterium anges i fältet **Direktleverans kräver plats**. Platsen på mötesschemat som hör till lasten kopplas till den slutgiltiga platsen för varor som direktutlevereras. Den slutgiltiga platsen för varor som direktutlevereras bestäms av platsdirektivet för **Överför leverans** för arbetsordertypen **Placera**. Det kan vara lämpligt att ange fältet **Direktleverans kräver plats** i ett scenario där färdiga varor endast ska direktutlevereras om ett släpfordon har tilldelats en vikdörr. I så fall flyttas varorna direkt från produktionsraden till släpfordonet. När ett släpfordon tilldelas vikdörren, tilldelar en användare platsen för mötesschemat och gör därför platsen tillgänglig för direktutleveransen I följande avsnitt förklaras två exempel.

#### Scenario 1 - Direktleverans från produktion till överföringsorder
<a id="scenario-1--cross-docking-from-production-to-transfer-orders" class="xliff"></a>

När en produkt som har rapporterats som avslutat på produktionsraden överförs den till en vikdörrplats där den lastas på en lastbil och överförs till ett distributionscenter. Använd företags-USMF.

1.  Aktivera en ny nummersekvens för direktutleverans. Gå till sidan **nummersekvenser** välj knappen **generera**. En guide hjälper dig geom processen.
2.  Skapa en direktleveranspolicy. Gå till sidan **Direktleveranspolicy** och skapa en ny policy med namnet **Direktleverans till överföringsorder**. Observera att den enda arbetsordertypen som du kan välja är **Överför leverans**, och den enda direktutleveransstrategin som finns är **datum och tid**.
3.  Skapa en arbetspolicy. Gå till sidan **arbetspolicyer** och skapa en ny arbetspolicy som heter **Direktutleverans L0101**.
4.  Ställ in laster så att de skapas automatiskt för överföringsorder. I lagerställeparametrarna anger du laster så att de skapas automatiskt när en överföringsorder skapas. En last är en förutsättning för att göra överföringsordern berättigad till direktutleverans.
5.  Konfigurera artikellastmappning. Gå till sidan **artikellastmappning** och skapa en standardlastmall för artikelgruppen **CarAudio**. Den här mappningen infogar automatiskt lastmallen när överföringsordern skapas.
6.  Skapa en internprisorder. Skapa överföringsordern för artikel nummer L0101. Kvantitet = 20
7.  Frisläpp överföringsorder från workbench för lastplanering. På fliken **transport** väljer du menyalternativet för workbench för lastplanering och på menyn för lastraden **frisläpp** , väljer **frisläpp till lagerställe**. En öppen påfyllnadsrad av typen **överför problem** finns nu för överföringsordern.
8.  Skapa en produktionsorder. Gå till listsidan **tillverkningsorder** och skapa en produktionsorder för produkten L0101. Kvantitet = 20 Uppskatta och starta produktionsordern. Observera att fältet **Bokför plocklista nu** är inställt på **Nej**.
9.  Rapportera som färdigt från den mobila enheten. Gå till portalen för den mobila enheten och välj menyalternativet **Rapportera som färdig och inlagrad**. Rapportera nu som färdig L0101 från den handhållna enheten. Observera att platsen är **BAYDOOR**. Den här platsen finns på platsdirektivet **Överför leverans** för arbetsordertypen **placera**. Lägg också märke till att arbete av typen **överför leverans** har skapats och slutförts. Gå till överföringsorderdetaljerna för att kontrollera arbetet.
10. Försök att starta 20 stycken fler på tillverkningsordern och försök sedan att rapportera 20 ea som färdig genom att använda handenheter. Denna tid, plats **LP-001** föreslås som platsen. Denna plats hittas i platsdirektivet för **Plats för slutförda varor**. Detta platsdirektiv används, eftersom det inte finns någon möjlighet för direktutleverans. Överföringsorder för LP-001 uppfylldes helt efter den första aktiviteten för direktutleverans.

Arbete av typen **Plats för slutförda varor** har skapats och bearbetats.

#### Scenario 2: direktutleverans från produktion till överföringsorder med ett mötesschema
<a id="scenario-2---cross-docking-from-production-to-transfer-orders-with-an-appointment-schedule" class="xliff"></a>

När en produkt har rapporterats som avslutad på produktionsraden överförs den till en vikdörrplats som identifieras av ett mötesschema för vikdörrplatserna. Använd företags-USMF.

1.  Ändra direktleveranspolicy. Ändra direktutleveranspolicyn som du skapade i scenario 1 genom att markera kryssrutan **Direktleverans kräver plats**.
2.  Skapa en ny överföringsorder.
3.  Öppna **workbench för lastplanering**.
4.  Från workbench för lastplanering går du till avsnittet **Laster** och markerar **Tidsplanera möte** på menyn **transport** om du vill skapa ett nytt mötesschema. Observera att mötesschemat innehåller en referens till överföringsordern i fältet **ordernummer**. I fältet **Planerat startdatum/tid på plats** kan du ange datum och tid för den avtalade tiden. Detta datum och denna tid används när direktutleveransefterfrågan prioriteras under direktutleveransprocessen. Det datum och den tid som du anger i det här fältet uppdaterar fältet **Datum och tid för tidsplanerad lastleverans** på motsvarande last. Platsen på snabbfliken **leveransinformation** anger platsen som levereras på överföringsordern.
5.  På **Workbench för lastplanering** frisläpper till lagret.
6.  Skapa en produktionsorder för artikelnummer **L0101**, och ange status till **startad**, med kvantiteten 20.
7.  Rapportera som färdigt från den mobila enheten.
8.  Gå till portalen för den mobila enheten och välj menyalternativet **Rapportera som färdig och inlagrad**.
9.  Rapportera nu som färdig **L0101** från den handhållna enheten. Observera att platsen nu är **BAYDOOR 2**. Den här platsen finns från mötesschemat i stället för ett platsdirektiv **Överföringsinleverans**.

### Ytterligare information
<a id="additional-information" class="xliff"></a>

-   Direktutleverans scenario stöds för batch- och seriekontrollerade element, både för batch- och serienummerdimensioner definierade ovan och under platsen i reservationshierarkin.
-   Den kvantitet som rapporteras som färdig kan inte delas till ett överföringsorderkrav som är lägre. Om exempelvis 20 stycken rapporteras som färdiga och en överföringsorder existerar för 5 stycken, så kommer överföringsordern inte att vara tillämplig för direktutleverans.


