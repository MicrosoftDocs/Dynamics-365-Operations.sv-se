---
title: Milstolpemallar
description: Det här ämnet beskriver hur du ställer in milstolpefakturering vid fakturering av abonnemang.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: d3c2cf751e4998c73bc3816e5b81e8d5963c8e53
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856782"
---
# <a name="milestone-billing"></a>Milstolpesfakturering

[!include [banner](../includes/banner.md)]

Den här artikeln förklarar hur du definierar mallar för funktionen för milstolpsfakturering i prenumerationsfakturering. Du kan definiera allokeringsprocent eller allokeringsbelopp för varje rad i milstolpemallen. Du kan sedan tilldela milstolpemallen till artiklar med faktureringsschema som använder faktureringsfunktionen för milstolpar.

## <a name="add-a-template"></a>Lägg till en mall

Följ dessa steg för att lägga till en milstolpsmall.

1. Gå till **Prenumerationsfakturering \> Återkommande kontraktsfakturering \> Konfigurera \> Milstolpar mallar**.
2. Välj **Ny**.
3. I fältet **Milstolpar mallar** anger du en unik identifierare för den nya mallen.
4. Ange en beskrivning i fältet **beskrivning**.
5. I fältet **Allokeringsmetod** välj allokeringsmetod.
6. Valfritt: Ange mallens **totalbelopp** i fältet summa belopp.
7. För att lägga till en rad, välj **Lägg till**. Välj sedan **artikelnummer** för den nya raden i fältet Artikelnummer.
8. Gör något av följande, beroende på vilket värde du valt i fältet **allokeringsmetod**:

    - Om du har valt **Procent** som allokeringsmetod anger du i **procent** anger du allkokeringsprocent för varje rad. Om du anger procentsatser måste summan av procenttalen som visas i fältet **Totalprocent** vara lika med **100**.
    - Om du har valt **Variabelt belopp** som allokeringsmetod anger du i **belopp** anger du belopp för varje rad.
    - Om du har valt **Lika med belopp** som allokeringsmetod behöver du inte ange ett belopp. Varje rad uppdateras med korrekt procentsats och belopp, baserat på antalet artiklar som läggs till i mallen.

9. Välj **Spara**.

## <a name="delete-a-template"></a>Ta bort mall

Följ dessa steg för att ta bort en milstolpsmall.

1. Välj en eller flera rader att radera och välj sedan **Ta bort**.
2. Om du uppmanas att bekräfta åtgärden väljer du **Ja**.

## <a name="milestone-template-fields"></a>Fält för milstolpemall

Sidan **mall för milstolpe** innehåller följande fält.

| Fält | Beskrivning |
|-------|-------------| 
| Milstolpemall | Den unika identifieraren av mall för milstolpe. |
| Beskrivning | Beskrivningen av mall för milstolpe |
| Allokeringsmetod | <p>Välj tilldelningsmetod:</p><ul><li>**Slutförandeprocent** – Ett ackumulerat slutförandevärde används för varje rad.</li><li>**Procent** – Ett procentbelopp kan anges för allokeringen. Summan av alla procentsatser måste vara lika med 100.</li><li>**Variabelbelopp** – Ett belopp kan anges för allokeringen. Allokeringsbeloppet anges på transaktionsnivå.</li><li>**Lika med belopp** – allokeringsprocenten beräknas automatiskt och delas lika mellan artiklarna i mallen.</li></ul> |
| Totalbelopp | Ange milstolpebeloppet för mallen. |
| **Rader** | |
| Artikelnummer | Välj artikelnummer för milstolpemallen. |
| Produktnamn | Namnet på artikeln. |
| Procentsats | <p>Ange allokeringsprocent för raden:</p><ul><li>Om fältet **Allokeringsmetod** är inställt på **Procent** anger du procentsatsen för raden.</li><li>Om fältet **Allokeringsmetod** ställs in på **Lika med belopp**, delas procenten automatiskt upp i lika delar, baserat på antalet artiklar i mallen.</li></ul><p>Summan av alla procentsatser måste vara lika med 100.</p><p>Om ett värde för **Totalt belopp** anges i rubriken och du ändrar värdet **Procent** för raden värdet **belopp** uppdateras. Om du ändrar värdet **belopp** kommer värdet **procent** uppdateras.</p> |
| Belopp | <p>Tilldelningsbeloppet för linjen:</p><ul><li>Om fältet **Allokeringsmetod** är inställt på **Variabelbelopp** anger du belopp för raden.</li><li>Om fältet **Allokeringsmetod** ställs in på **Lika med belopp**, delas beloppet automatiskt upp i lika stora belopp, baserat på antalet poster i mallen och **Total belopp** som anges i rubriken.</li></ul><p>Summan av alla belopp måste vara lika med det **totala belopp** värde som anges i rubriken.</p><p>Om ett värde för **Totalt belopp** anges i rubriken och du ändrar värdet **Belopp** för raden värdet **procent** uppdateras. Om du ändrar värdet **procent** kommer värdet **belopp** uppdateras.</p> |
| **Summor** | |
| Total procent | Summan av procentsatserna. Summan av alla procentsatser måste vara lika med 100. |
| Totalbelopp | Summan av värdet **Belopp** för alla rader. Summan måste vara lika med det **totala belopp** värde som anges i rubriken. |
| Resterande belopp | Resterande belopp. Värdet beräknas som värdet **Totalt belopp** från rubriken minus summan av värdet **Belopp** för alla rader.|

## <a name="milestone-allocation"></a>Milstolpeallokering

Innan du börjar använda milstolpefunktionen bör du utföra de här uppgifterna.

1. Lägg till en eller flera milstolpemallar.
2. Skapa en grupp för faktureringstidsplan. Ange **Milstolpe** som artikeltyp och välj en mall.
3. På sidan **Artikelinställning** (**Prenumerationsfakturering \> Återkommande kontraktsfakturering \> Inställning \> Artiklar**), välj en artikelrelation och en milstolpsmall för artikelinställningen.

När du har skapat milstolpemallar, faktureringsschemagrupper och artiklar, kan du skapa ett faktureringsschema där milstolpefunktionen används.

Skapa ett faktureringsschema där milstolpar används genom att följa stegen nedan.

1. I listan **Alla/Aktiva faktureringsscheman** på sidan **Faktureringsscheman** välj **Vy**.
2. På sidan **Alla faktureringsscheman** skapa ett nytt faktureringsschema och ange ett kundkonto och ett startdatum.
3. I avsnittet **faktureringsschemarader** välj **Lägg till rad**. Lägg sedan till ett artikelnummer och ställ in fältet **Artikeltyp** på **Milstolpe**.

    Om en standardmall för milstolpar ställs in för artikeln, läggs milstolpehändelser automatiskt till på raderna i faktureringsschemat. Slutdatum är tomma för milstolperader.

    Om ingen milstolpemall har ställts in för artikeln väljer du **Milstolpeallokering** . Sedan på sidan **Milstolpe allokering** väljer du sedan en milstolpemall och gör de uppdateringar som behövs. Välj sedan Stäng **för** att återgå till faktureringsschemat och slutför skapandet av faktureringsschemat.

4. Om du vill skapa fakturor för faktureringsplanen måste du uppdatera slutdatumet för varje milstolpehändelse. För ett enstaka faktureringsschema kan du uppdatera slutdatumet för milstolpehändelsen på raderna i faktureringsschemat. Om du vill uppdatera flera faktureringsscheman väljer du **Uppdatera slutförandedatumprocess**.
5. När slutdatumet har uppdaterats kan du skapa fakturan. Om du vill ha ett enda faktureringsschema väljer du **Generera faktura** på sidan **Alla faktureringsscheman**. Om du vill skapa fakturor för flera faktureringsscheman väljer du **Generera faktura** eller **Skapa batchbearbetning** av fakturor under **Periodiska uppgifter**.

## <a name="edit-milestone-allocation-on-a-billing-schedule-line"></a>Redigera milstolpeallokering på en faktureringsplansrad

Följ dessa steg för att redigera milstolpetilldelning på en faktureringsschemarad.

1. På sidan **faktureringsschema** > **Alla eller aktiva faktureringsscheman**, i fältet **faktureringsschemat**, välj schemanummer för faktureringsschemat.
2. I avsnittet **faktureringsschemarader** ange ett objekt, specificera **Milstolpe** som objekt och välj **Milstolpeallokering**.
3. I fältet **milstolpemall** välj en milstolpemall.
4. Välj **Process**. Milstolpemallraderna läggs automatiskt till på raderna i faktureringsplanen.

## <a name="milestone-allocation-fields"></a>Fälten milstolpeallokering

Sidan **Milstolpeallokering** innehåller följande fält.

| Fält | Beskrivning |
|-------|-------------|
| Överordnad artikel | Förälderns artikelnummer. |
| Slutligt pris | <p>Det utökade priset på föremålet. Värdet motsvarar **nettobeloppvärdet** för faktureringsschemaraden.</p></p>För en överordnad milstolpeartikel är standardvärdet det **totala belopp** värdet som har angetts för milstolpemallen. Om det totala beloppet är 0 (noll) är standardvärdet **nettobeloppet** för faktureringsschemaraden.</p> |
| Milstolpemall | Milstolpsmall-ID för radobjekten. |
| Mallbeskrivning | Beskrivningen av mall för milstolpe |
| Allokeringsmetod | Allokeringsmetoden som används för milstolpemallen. |
| **Rader** | Standardvärdena för alla rader baseras på den valda milstolpemallen. Du kan ändra dem efter behov. |
| Artikelnummer | Artikelnumret för milstolpetilldelningsmallen. |
| Produktnamn | Produktnamnet. |
| Procentsats | <p>Allokeringlokeringsprocent för raden:. Summan av alla procentsatser måste vara lika med 100.</p><p>Om du ändrar värdet **procent** kommer värdet för rad **nettobelopp** uppdateras. Om du ändrar värdet **Nettobelopp** kommer värdet **Procentsats** uppdateras.</p> |
| Nettobelopp | <p>Tilldelningsbeloppet för linjen. Summan av nettobelopp för alla rader måste vara lika med **Slutligt pris** värde som anges i rubriken.</p><p>Om du ändrar värdet **nettobelopp** kommer värdet för rad **Procentsats** uppdateras. Om du ändrar värdet **procent** kommer värdet **Nettobelopp** uppdateras.</p> |
| **Summor** | |
| Total procent | Summan av värdet **Procentsats** för alla rader. Denna summa måste vara lika med 100. |
| Totalbelopp | Summan av värdet **Nettobelopp** för alla rader. Summan måste vara lika med det **Slutligt pris** värde som anges i rubriken. |
| Resterande belopp | Resterande belopp. Värdet beräknas som värdet **Slutligt pris** från rubriken minus summan av värdet **Nettobelopp** för alla rader. Det slutliga beloppet måste vara 0 (noll). |
