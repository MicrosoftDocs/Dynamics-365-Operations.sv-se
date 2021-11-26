---
title: Ursprungsland
description: Många organisationer utfärdar certifikat till sina leverantörer för att säkerställa att produkterna uppfyller specifika certifieringsstandarder. Dessa certifikat beror ofta på ursprungslandet. Det här avsnittet innehåller information om funktionens ursprungsland där du kan koppla en produkt till dess ursprungsland och hålla reda på produktens certifiering.
author: t-benebo
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: a2740f6b1ccb52073b013e613d8ab779cc088180
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777648"
---
# <a name="country-of-origin"></a>Ursprungsland

[!include [banner](../includes/banner.md)]

Många organisationer utfärdar certifikat till sina leverantörer för att säkerställa att produkterna uppfyller specifika certifieringsstandarder. Dessa certifikat beror ofta på ursprungslandet. Funktionens ursprungsland där du kan koppla en produkt till dess ursprungsland och hålla reda på produktens certifiering.

## <a name="turn-on-the-country-of-origin-feature"></a>Aktivera funktionen för ursprungsland

Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Administratörer kan använda sidan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera/inaktivera den vid behov. Här visas funktionen i listan:

- **Modul:** *Produktinformationshantering*
- **Funktionsnamn:** *funktionen hantering av ursprungsland*

## <a name="configure-source-and-destination-countries"></a>Konfigurera käll- och målländer

Innan du utfärdar ett certifikat för en produkt måste du länka produkten till mållandet och ursprungslandet.

1. Gå till **Produktinformationshantering \> Inställningar \> Produktefterlevnad \> Ursprungsland \> Ursprungslandets regler**.
2. Välj en befintlig landsinställning för att redigera, eller välj **ny** i åtgärdsfönstret för att skapa en ny landsinställning.
3. Ange följande värden för det valda eller nya landet.

    | Fält | beskrivning |
    |---|---|
    | Artikelnummer | Välj produktens artikelnummer. |
    | Destinationsland | Välj det land som du ska skicka produkten till. |
    | Ursprungsland | Välj det land som du ska skicka produkten från. |

Syftet med den här inställningen är att hjälpa dig att generera en strukturlista (BOM) där du kan inkludera ursprungslandet för varje del som käll- och målländer har angetts för. I den här rapporten får du hjälp att få en helhetsbild av var dina delar kommer och var de kommer.

## <a name="keep-track-of-vendor-certificates"></a>Hålla reda på leverantörscertifikat

Du kan använda sidan **leverantörscertifikat för ursprungslandet** för att hålla reda på de certifikat som du skickar till leverantörerna.

Du måste bestämma vilka certifikat som du ska utfärda och hur de ska rapporteras till kunderna. Med hjälp av den här funktionen kan du hålla reda på dina certifikat. Du kan också välja om de relevanta certifikatnumren visas på fakturor, följesedlar och/eller orderbekräftelser.

Så här ställs certifikatinformation in.

1. Gå till **Produktinformationshantering \> Inställningar \> Produktefterlevnad \> Ursprungsland \> Ursprungslandets leverantörscertifikat**.
2. Välj en befintlig certifikatinställning för att redigera, eller välj **ny** i åtgärdsfönstret för att skapa en ny certifikatinställning.
3. Ange följande inställningar för det valda eller nya certifikatet.

    | Fält | beskrivning |
    |---|---|
    | Leverantörskonto | Välj den leverantör som du har utfärdat certifikatet till. |
    | Artikelnummer | Välj det objekt leverantör som du har utfärdat certifikatet för. |
    | Land/region | Destinationsland eller -region där du måste använda det här certifikatet. |
    | Certifikatnummer | Ange ID-numret för det certifikat som du har utfärdat. |
    | Giltighet | Välj det första datumet när det aktuella certifikatet är giltigt.|
    | Förfallotid | Välj det sista datumet när det aktuella certifikatet är giltigt. |
    | Skriv ut på faktura | Markera den här kryssrutan om du vill skriva ut certifikatnumret på fakturor som är adresserade till det angivna landet under det angivna datumintervallet. |
    | Skriv ut på följesedel | Markera den här kryssrutan om du vill skriva ut certifikatnumret på följesedel som är adresserade till det angivna landet under det angivna datumintervallet. |
    | Skriv ut på försäljningsorder | Markera den här kryssrutan om du vill skriva ut certifikatnumret på försäljningsorder som är adresserade till det angivna landet under det angivna datumintervallet. |

## <a name="include-the-country-of-origin-on-bom-reports"></a>Inkludera ursprungslandet i strukturlisterapporter

När du genererar en strukturlisterapport kan du inkludera ursprungslandet för varje del som du har angett käll- och målländer för sidan **Regler för ursprungsland**.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj eller skapa en produkt för att öppna dess sida **Information om frisläppt produkt**.
1. I Åtgärdsfönstret, på fliken **Konstruera**, i gruppen **Strukturlista**, markerar du **Designer**.
1. På den sida som visas väljer du **Strukturlista \> Skriv ut** i åtgärdsfönstret.
1. I dialogrutan **strukturlisterader** ange fältet **målland** till det målland som du vill visa i rapporten.
1. Välj **OK**.

En rapport som visar information om ursprungslandet för varje del genereras och visas. Här följer ett exempel på rapporten.

![Rapport för ursprungsland.](media/country-of-origin-report.png "Ursprungsland, rapport")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]