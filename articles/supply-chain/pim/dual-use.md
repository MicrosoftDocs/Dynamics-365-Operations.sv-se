---
title: Varor med dubbla användningsområden
description: I det här avsnittet beskrivs hur du håller reda på produkter som identifieras som produkter med dubbla användningsområden, lagrar certifikatnummer för varje relevant produkt och målland och skriver ut giltiga certifikatnummer på relevanta fakturor, följe sedlar och/eller försäljningsorder.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: COODualUseCerts, COORules, COODualUseCountries
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: a6cc730f8d672d906072a9b97b737dbdea9faf2d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243211"
---
# <a name="dual-use-goods"></a>Varor med dubbla användningsområden

[!include [banner](../includes/banner.md)]

Produkter med dubbla användningsområden är vanligtvis objekt som har både civila och militära tillämpningar. En kemikalie kan t.ex. användas antingen som ett gödselmedel eller vara explosiv. Många länder har särskilda bestämmelser som gäller för export, import och transport av produkter med dubbla användningsområden. Därför är det viktigt att företag som ingår i den internationella handeln med produkter med dubbla användningsområden håller ordning på de olika principerna och intygen.

Med funktionen för dubbel användning håller du reda på produkter som identifieras som produkter med dubbla användningsområden, lagrar certifikatnummer för varje relevant produkt och målland och skriver ut giltiga certifikatnummer på relevanta fakturor, följe sedlar och/eller försäljningsorder. Det säkerställer att när dina produkter levereras tar de alltid upp aktuella certifieringar.

Tänk på följande scenario:

1. Sidan **Landsinställning för dubbel användning** i ditt system indikerar att leveranser till Frankrike kräver en certifiering.
2. Sidan **Information om frisläppt produkt** för produkt X-100 visar att det är ett bra användningssystem. Tillsammans visar koden, kategorin, gruppen och ordningen den export kontrollklassificering som produkten tillhör.
3. På sidan **Certifikat för dubbel användning** inkluderar ett certifikat för produkt X-100 när den skickas till Frankrike. Det här certifikatet upphör att gälla 1 januari 2020.
4. Den 17 juni 2020 skapar du en försäljningsorder för ett kundföretag som är baserat på Frankrike och ordern inkluderar produkt X-100.
5. När du sparar försäljningsordern avgör systemet följande information:

    1. Omfattar ordern alla produkter som är varor som är med dubbla användningsområden?
    2. Om ordern innehåller produkter med dubbla användningsområden kräver mållandet att använda certifikat med dubbla användningsområden?
    3. Om landet kräver certifikat med dubbla användningsområden, finns det ett giltigt certifikat för varje bra användning för mållandet?

6. I ordern ingår produkt X-100, produkten levereras till Frankrike och det finns ett franskt certifikat för produkten. Certifikatet har dock upphört att gälla. Därför visas följande varningsmeddelande: "dubbel användningscertifikat för ett eller flera artiklar med dubbla användningsområden i den här försäljningsordern är inte giltiga. Vill du fortsätta med bekräftelsen?"

I det här avsnittet beskrivs hur du konfigurerar alla inställningar som krävs för att ställa in produkter med dubbla användningsområden och stöd för det här scenariot.

## <a name="define-dual-use-requirements-for-each-relevant-country"></a>Definiera krav för dubbla användningsområden för varje relevant land

Olika länder har olika krav för produkter med dubbla användningsområden. Du använder sidan **Landsinställning för dubbel användning** för hålla reda på vilka länder som behöver och inte behöver ett certifikat. Den information som du anger här kontrolleras när du skapar försäljningsorder och du får en påminnelse om att ge de nödvändiga certifieringarna.

Om du vill ställa in information om kraven för dubbla användningsområden för olika länder följer du stegen nedan.

1. Gå till **Produktinformationhantering \> Inställningar \> Produktenskompatibilitet \> Produkter med dubbla användningsområden \> Landsinställning för dubbel användning**.
2. Välj en befintlig landsinställning för att redigera, eller välj **ny** i åtgärdsfönstret för att skapa en ny landsinställning.
3. Ange följande värden för det valda eller nya landet.

    | Fält | beskrivning |
    |---|---|
    | Land/region | Välj det land som du vill följa upp krav för. |
    | Intyg krävs | Markera den här kryssrutan för länder som kräver certifiering för produkter med dubbla användningsområden. Avmarkera det för länder som inte behöver denna certifiering. |

## <a name="create-dual-use-categories"></a>Skapa kategorier med dubbla användningsområden

Produkter med dubbla användningsområden måste ofta kategoriseras enligt export kontroll klassificeringsnummer (ECCN). ECCN är en alfanumerisk kod som kategoriserar artiklar baserat på faktorer som vara och teknik. Sidan **kategorier med dubbla användningsområden** hjälper dig att skapa en lista över de kategorier som du använder för rapporteringssyfte.

Så här ställer du in kategorier med dubbla användningsområden.

1. Gå till **Produktinformationhantering \> Inställningar \> Produktenskompatibilitet \> Produkter med dubbla användningsområden \> kategorier med dubbla användningsområden**.
2. Välj en befintlig kategori för att redigera, eller välj **ny** i åtgärdsfönstret för att skapa en ny kategori.
3. Ange följande värden för det valda eller nya kategori.

    | Fält | beskrivning |
    |---|---|
    | Kod för dubbel användning | Ange den fullständiga ECCN-koden (till exempel *3A001*).|
    | Kategori för dubbel användning | Ange listan över Commerce Control List (CCL) i ECCN-koden. Till exempel för ECCN-kod *3A001* är värdet *3*. |
    | Grupp för dubbel användning | Ange produktgruppsdelen i ECCN-koden. Till exempel för ECCN-kod *3A001* är värdet *A*. |
    | Ordning för dubbel användning | Ange ordning för artikeln. Den här koden identifierar skälet till att en artikel klassificeras som en vara med dubbla användningsområden. Till exempel för ECCN-kod *3A001* är värdet *001*. |

## <a name="apply-dual-use-categories-to-products"></a>Tillämpa kategorier med dubbla användningsområden på produkter

Om du vill identifiera en produkt som vara med dubbla användningsområden och tillämpa en kategori med dubbla användningsområden för den följer du stegen nedan.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj eller skapa en produkt för att öppna dess sida **Information om frisläppt produkt**.
1. Snabbfliken **Utrikeshandel** anger du alternativet **Produkter med dubbla användningsområden** till **Ja** för att identifiera den aktuella produkten som ett dubbla användningsområden.
1. Ställ in fältet **Kod för dubbel användning** till den kod som gäller för den aktuella produkten. (Du definierade den här koden på sidan **Kategorier med dubbla användningsområden** .)

Den här inställningen kontrolleras när du skapar en försäljningsorder.

## <a name="set-up-dual-use-certificates"></a>Ställa in certifikat med dubbla användningsområden

Använd sidan **Certifikat för dubbel användning** när du vill ställa in och hantera de krävda certifikaten för dubbel användning för varje produkt och land. Du kan spåra varje certifikats detaljer, t.ex. landet och giltighetsdatumet. Du kan också ange alternativ för att ange var den här informationen ska skrivas ut. Informationen kan till exempel skrivas ut på fakturan, följesedeln och/eller försäljningsordern. Den här inställningen kontrolleras när du skapar en försäljningsorder.

1. Gå till **Produktinformationhantering \> Inställningar \> Produktenskompatibilitet \> Produkter med dubbla användningsområden \> Certifikat med dubbla användningsområden**.
2. Välj ett befintligt certifikat för att redigera, eller välj **ny** i åtgärdsfönstret för att skapa ett nytt certifikat.
3. Ange följande värden för det valda eller nya certifikatet.

    | Fält | beskrivning |
    |---|---|
    | Artikelnummer | Välj artikelnummer för det som det här certifikatet gäller för dubbel användning. |
    | Land/region | Destinationsland eller -region där du måste använda det här certifikatet. |
    | Certifikatnummer | Det nummer som visas på certifikatet som har skickats till leverantören eller kunden. |
    | Giltighet | Välj det första datumet när det aktuella certifikatet är giltigt.|
    | Förfallotid | Välj det sista datumet när det aktuella certifikatet är giltigt. |
    | Skriv ut på faktura | Markera den här kryssrutan om du vill skriva ut certifikatnumret på fakturor som är adresserade till det angivna landet under det angivna datumintervallet. |
    | Skriv ut på följesedel | Markera den här kryssrutan om du vill skriva ut certifikatnumret på följesedel som är adresserade till det angivna landet under det angivna datumintervallet. |
    | Skriv ut på försäljningsorder | Markera den här kryssrutan om du vill skriva ut certifikatnumret på försäljningsorder som är adresserade till det angivna landet under det angivna datumintervallet. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]