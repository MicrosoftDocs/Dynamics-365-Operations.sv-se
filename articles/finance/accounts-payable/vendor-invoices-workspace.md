---
title: Arbetsyta för automatisering av leverantörsfaktura
description: I det här avsnittet beskrivs hur du ställer in en arbetsyta som är relaterad till leverantörsfakturor och som visar den information som är tillgänglig via Microsoft Power BI.
author: abruer
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2020-09-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f28cc5f63df2f0d8a4c8cae407f7166aa4fa03db
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182589"
---
# <a name="vendor-invoice-automation-workspace"></a>Arbetsyta för automatisering av leverantörsfaktura

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs hur du ställer in en arbetsyta som är relaterad till leverantörsfakturor och som visar den information som är tillgänglig via Microsoft Power BI. Informationen om leverantörsfakturor på den här arbetsytan filtreras för specifika användare och visas i ett grafiskt format.

## <a name="overview"></a>Översikt

Arbetsytan **Automatisera leverantörsfaktura** visar information kopplad till behandling av leverantörsfaktura. Den innehåller vyn **Mitt arbete** och sidan **Analyser – alla företag**. Vyn **Mitt arbete** visar sammanfattningsrutor, rutnät för leverantörstransaktioner och relaterad leverantörsinformation. Sidan **Analyser – alla företag** använder funktionerna i Power BI för att visa visualiseringar relaterade till leverantörsfakturor.

## <a name="set-up-the-workspace-to-show-power-bi-content"></a>Ställ in arbetsytan för att visa Power BI-innehåll

Du måste slutföra den här inställningen innan data kan visas i Power BI-visualiseringar på arbetsytan **Automatisera leverantörsfaktura**.

1. I arbetsytan **funktionshantering** filtrerar du listan för att hitta funktionen **automatisering av leverantörsfakturor**.
3. Välj **Aktivera nu**.
4. Om du vill försäkra dig om att fakturor kan bearbetas från början till slut utan att behöva handläggas, ställer du in ett arbetsflöde för leverantörsfakturor För att ställa in ett arbetsflöden, gå till **Leverantörsreskontra \> Inställningar \> Arbetsflöden för leverantörsreskontra**.
5. Gå till **Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra** och välj fliken **Automation av leverantörsfaktura**. För mer information, se [Konfigurera alternativ för automatisering av leverantörsfakturor](vnd-invoice-set-up-options.md).
6. Ange alternativet **Skicka importerade fakturor automatiskt till arbetsflödet** till **Ja**.
7. Om produktinleveranser automatiskt ska matchas ställer du in alternativet **Matcha produktkvitton automatiskt till fakturarader** till **Ja**.
8. Granska de återstående, valfria inställningarna och konfigurera dem enligt organisationens krav.
9. Gå till **Systemadministration \> Inställningar \> Systemparametrar** och ställ in **Systemvaluta** och **Systemets valutakurs**.
10. Gå till **Redovisning \> Inställningar \> Redovisning** och ange fälten **redovisningsvaluta** och **valutakurstyp**.
11. Gå till **Redovisning \> Valutor \> Valutakurser**, och ange valutakurserna mellan transaktionsvalutan och redovisningsvalutan och mellan redovisningsvalutan och systemvalutan.
12. Gå till **Systemadministration \> Inställningar \> Enhetslagring** och sök efter **Åtgärd för automatisering av leverantörsfaktura**. Välj **uppdatera**.

Om du vill visa den information som visas på arbetsytan måste du ha säkerhetsrollen Leverantörsreskontrachef eller Leverantörsreskontraansvarig.

## <a name="my-work-view"></a>Vyn Mitt arbete

### <a name="company-selection"></a>Företagsval

När funktionen **Automatisera leverantörsfakturor** är aktiverad visas fältet **Företag** högst upp på arbetsytan. Valet i fältet **Företag** påverkar all information som visas på arbetsytan. Som standard visar vyn information för det företag som du har loggat in på. Genom att välja ett annat företag i fältet **företag** kan du visa information för det företaget på arbetsytan. Du kan sedan välja en panel på arbetsytan för att gå till den relaterade sidan i det valda företaget.

### <a name="summary-tiles"></a>Sammanfattningsrutor

Panelerna i avsnittet **Sammanfattning av väntande fakturor** i vyn **Mitt arbete** ger en översikt över statusen för leverantörsfakturorna. Du kan visa journaler som ännu inte har bokförts och fakturor som är spärrade. Det finns dessutom fyra paneler som är kopplade till funktionen automatisering av leverantörsfaktura:

- **Manuell inleveransmatchning krävs**
- **Matchningsvalideringen lyckades inte**
- **Inga fakturor har skickat till arbetsflödet**
- **Inga fakturor har importerats**

(De fyra panelerna kräver att funktionen för automatisering av leverantörsfakturor aktiveras i **funktionshantering**.)

Om du vill använda panelen **Återställ leverantörsfakturor** måste funktionen vara aktiverad i **leverantörsparametrar**. Gå till **leverantörsreskontra \> parametrar för leverantörsreskontra** och ställ sedan in fliken **faktura** ange alternativet **tillåt återställning av leverantörsfaktura** till **Ja**.

När funktionen är aktiverad visas också tre paneler som grupperats på arbetsytan i ett avsnitt med namnet **journaler**. Panelerna heter **Journaler**, **Journaler – tilldelade till mig** och **Fakturapool**. 

Informationen i avsnittet **Sammanfattning av väntande fakturor** för företaget som anges som standardföretag för inloggningen.

### <a name="creating-new-records"></a>Skapa nya registreringar

Om du vill skapa en ny fakturapost väljer du **ny** och väljer sedan en av följande posttyper i listan:

- Leverantörsfaktura
- Fakturajournal
- Global fakturajournal
- Fakturaregister
- Godkännande av faktura

Observera att den post du skapar baseras på företagsfiltret, inte det företag som du är inloggad på. Du är t.ex. inloggad på **UMSF** företaget, men företagsfiltret är inställt på **GBSI**. I detta fall när du väljer **Ny** och sedan väljer en posttyp i listan, skapas posten i GBSI-företaget.

### <a name="documents-not-invoiced-grids"></a>Dokument utan fakturerade rutnät

Avsnittet **dokument som inte är fakturerade** innehåller rutnät som visar dokument som väntar på leverantörsfakturor.

I rutnätet **öppna inköpsorder** visas alla inköpsorder som ännu inte har fakturerats helt. Du kan använda knappen **fakturera nu** om du vill skapa en leverantörsfaktura för en inköpsorder. Du kan använda knappen **Förskottsfaktura nu** om du vill skapa en förskottsfaktura för en inköpsorder.

I rutnätet **Produktinleveranser** visas alla produktinleveranser för inköp som ännu inte har fakturerats helt. Du kan använda knappen **fakturera nu** om du vill skapa en leverantörsfaktura för en inköpsorder.

Rutnätet **väntande leverantörsfakturor** visar alla leverantörsfakturor som inte har skickats till arbetsflödessystemet. Du kan använda fältet **Sök** fältet och/eller företagsfiltret för att söka efter en viss leverantörsfaktura. Du kan använda knappen **Redigera** om du vill redigera en transaktion som visas i rutnätet.

I rutnätet **Söka efter inköpsorder** kan du använda fältet **Sök** för att söka efter en viss inköpsorder.

### <a name="related-information"></a>Relaterad information

Du kan visa information om bokförda fakturor genom att använda länkarna på höger sida av arbetsytan. Dessa länkar inkluderar **Öppna leverantörsfakturor**, **Fakturajournal** och **Fakturahistorik och matchningsuppgifter**. I avsnittet **leverantörer** kan du komma åt en filtrerad lista som visar alla leverantörer som är i vänteläge, eller så kan du använda **Alla leverantörer**. Länkarna **Alla inköpsorder** och **Öppna för förskottsbetalning** är också tillgängliga.

### <a name="analytics--all-companies-page"></a>Sidan analyser – alla företag

När alternativet **Skicka importerade fakturor automatiskt till arbetsflödet** anges till **Ja** på sidan **Parametrar för leverantörsreskontra** kan du visa automatiseringsanalys. Sidan **Analys – alla företag** innehåller viktiga mått, t.ex. leverantörsfakturor som har godkänts av godkännaren och av företaget. Denna sida innehåller fem rapportsidor. En sida ger en översikt och de andra sidorna ger information om statistik över automatisering av leverantörsreskontra.

Följande tabell visar de visulaiseringar som är tillgängliga på varje rappportsida.

| Rapportsida                    | Visualiseringar |
|--------------------------------|----------------|
| Översikt över leverantörsfakturor        | <ul><li>Väntande leverantörsfakturor i automatisering i systemvalutan</li><li>Fakturor som inte kunde importeras</li><li>Fakturor i arbetsflöde</li><li>Beröringslösa fakturor de senaste 30 dagarna</li><li>Totalt antal automatiska fakturor de senaste 30 dagarna</li><li>Saldo för öppna fakturor i systemvaluta</li><li>Orsaker till fel, de senaste 30 dagarna</li><li>Procent av bokförda fakturor som har bearbetats automatiskt</li><li>Antal dagar att bearbeta en faktura</ul></li> |
| Automationsstatus              | <ul><li>Beröringslösa fakturor de senaste 30 dagarna</li><li>Beröringslösa fakturor de senaste 30 dagarna efter företag</li><li>Beröringslösa fakturor de senaste 30 dagarna efter leverantörsgrupp</li><li>Procent av bokförda fakturor som har bearbetats automatiskt</li><li>Antal dagar att bearbeta en faktura</li></ul> |
| Fakturor som inte kunde importeras | <ul><li>Fakturor som inte kunde importeras</li><li>Fakturor som inte kunde importeras efter företag</li></ul> |
| Orsaker till automatiseringsfel | <ul><li>Fakturor misslyckades</li><li>Fakturorna misslyckades av företaget</li><li>Fakturor som misslyckades av leverantörsgrupp</li></ul> |
| Arbetsflödesstatus                | <ul><li>Fakturor i arbetsflöde</li><li>Instanser av arbetsflöde för leverantörsfaktura</li><li>Tilldelning per godkännare</li><li>Arbetsflöde för leverantörsfakturor per företag</li><li>Genomsnittligt antal dagar i arbetsflödet per godkännare</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
