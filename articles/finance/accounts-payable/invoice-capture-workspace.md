---
title: Arbetsyta för lösningen Invoice Capture
description: Den här artikeln innehåller information om den arbetsytan för lösningen Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4f3af7abf94542437be6132344d6bb7ffaf33d07
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691189"
---
# <a name="invoice-capture-solution-workspace"></a>Arbetsyta för lösningen Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="side-by-side-viewer-for-the-invoice-capture-solution"></a>Visningsprogrammet sida vid sida för lösningen Invoice Capture

Att registrera fakturor i systemet har vanligtvis varit en tidskrävande process som tar tid att hitta fel, eftersom de som använder dem måste navigera i flera bifogade filer och fönster för att kunna samla in rätt information. Dokumentvisningsprogrammet sida vid sida underlättar din erfarenhet när du arbetar på fakturor, genom att göra processen enklare, mer effektiv och mer korrekt.

I dokumentvisningsprogrammet sida vid sida kan användare öppna originaldokumentet och fakturan sida vid sida i samma fönster. Fakturasidan fylls i med information som kommer från det ursprungliga fakturadokumentet. Visaren bygger kopplingen mellan fälten på fakturasidan och det ursprungliga fakturadokumentet. Visaren hjälper användarna också att hitta eventuella fel på fakturasidan.

### <a name="open-the-side-by-side-viewer"></a>Öppna visningsprogram för sida-vid-sida

I Microsoft Dynamics 365 Finance kan du öppna visningsprogrammet sida vid sida från listan på sammanfattningssidan eller från listsidan för fakturor. Du kan också öppna den genom att dubbelklicka på en post eller välja fakturanumret.

### <a name="using-the-side-by-side-viewer"></a>Använda visningsprogram för sida-vid-sida

#### <a name="manually-review-an-invoice"></a>Granska en faktura manuellt

Ett fakturadokument som har importerats kanske måste granskas manuellt på grund av fel eller varningar. I visningsprogrammet sida vid sida visar dokumentrubriken statusen **Importerad** och den aktuella versionen blir **Ursprunglig version**.

Om du vill börja granska fakturan väljer du **Starta granskning**. Alla fält kan redigeras. Fältet **Status** uppdateras till **Under granskning** och fältet **Aktuell version** uppdateras till **Ändrad version**.

#### <a name="view-and-work-with-messages"></a>Visa och arbeta med meddelanden

Användarna bör starta granskningsprocessen från meddelandefönstret. Felmeddelanden indikeras av ett rött X, varningsmeddelanden indikeras av en triangel och informationsmeddelanden indikeras av en cirkel. Förtroendepoängrelaterade meddelanden kan klassificeras som antingen varningar eller fel, beroende på vilket tröskelvärde som anges av konfigurationsgruppen. Mer information finns i [Konfigurationsgrupper för lösning för Invoice Capture](invoice-capture-config-group.md).

Varnings- och felmeddelanden kan ignoreras från meddelandefönstret, fakturahuvudet eller fakturaraderna. När ett meddelande har ignorerats visas det inte längre som ett fel eller en varning och fakturan kommer inte att misslyckas validering.

- Välj **Ignorera** om du vill ignorera meddelanden i meddelandefönstret. Om du vill återställa ett meddelande som har ignorerats väljer du **Ignorera** igen. Typen ändras sedan från fel eller varning till information.
- Om du vill ignorera meddelanden från fakturahuvudet eller fakturaraden väljer du **Ignorera** i fältet. Meddelandesymbolen försvinner. Meddelandet visas dock igen om det återställs från meddelandefönstret.

För meddelanden som är relaterade till fält i fakturahuvudet flyttas markören till motsvarande fält i rubrikavsnittet när du väljer meddelandet i meddelandefönstret.

#### <a name="proofread-and-edit-fields"></a>Korrekturläsa och redigera fält

Om ett fälts värde läses från den ursprungliga fakturan via optisk teckenläsning (OCR) visas en symbol i fältet. Om du väljer symbolen zoomar dokumentvisning in och markerar platsen som fältvärdet läses från för att verifiera fakturadata.

Om du vill återställa dokumentvisningen till den ursprungliga förstoringen gör du på ett av följande sätt:

- Välj samma symbol som du tidigare har valt.
- Välj knappen i det övre högra hörnet av dokumentvisaren.

Redigera fälten efter behov. Redigeringar sparas automatiskt när markören lämnar ett fält. En symbol till höger om ett fält visar att fältet har uppdaterats manuellt. När sidan uppdateras tas symbolen bort.

#### <a name="check-an-invoice-to-get-up-to-date-messages"></a>Kontrollera en faktura för att få aktuella meddelanden

När du redigerar ett fält uppdateras fältvärdet, men nya valideringsmeddelanden genereras inte. För att få uppdaterade valideringsmeddelanden, välj **Kontrollera**. Meddelandena i meddelandefönstret, i fakturahuvudet och på fakturaraderna uppdateras.

#### <a name="complete-the-review"></a>Slutför recensionen

Slutför granskningen genom att välja **Slutför granskning**. Fakturorna valideras. Om några fel hittas förblir dokumentstatusen **Granskad** och ett meddelandefält visas. Alla meddelanden i meddelandefönstret och i fakturahuvudet och på raderna uppdateras automatiskt så att de ger information om orsaker till valideringen som misslyckades.

När alla spärrfel har åtgärdats kan granskningen slutföras. Dokumentstatus uppdateras till **Granskad** och fälten kan inte längre redigeras. Du kan starta om granskningen genom att välja **Starta granskning** igen.

#### <a name="generate-a-pending-vendor-invoice-in-finance"></a>Generera en väntande leverantörsfaktura i Ekonomi

Om du vill skicka fakturadokumentet till den anslutna ekonomimiljön väljer du **Generera**. Om fakturagenereringen misslyckas visas ett felmeddelande i ett meddelandefält.

#### <a name="void-an-invoice"></a>Annullera en faktura

Om du vill annullera en faktura väljer du **Annullera**. Annullerade fakturor kan inte granskas och visas inte i listan **Fakturor behöver granskas manuellt**.

### <a name="validation-logic"></a>Valideringslogik

Vissa nyckelfält i visningsprogrammet sida vid sida finns inte i faktura mellanlagringsdata, men de krävs för att generera väntande fakturor i Ekonomi. Dessa fält hämtas från en kombination av aktuella faktura mellanlagringsdata och huvuddata från Ekonomi.

Fälten som måste härledas är **Juridisk person**, **Leverantörskonto** och **Artikelnummer**. De måste härledas i följande ordning. Om ett fälts arbete misslyckas stoppas processen.

1. **Juridisk enhet** – Den juridiska personen hämtas först. Om en aktiv mappningsregel hittas för den juridiska personen hämtas den juridiska personen utifrån företagsnamnet och företagets adress.
2. **Leverantörskonto** – Sedan hämtas leverantörskontot utifrån en aktiv mappningsregel och en kombination av den härledda juridiska personen och leverantörens namn och leverantörsadress.
3. **Artikelnummer** – Slutligen hämtas artikelnamnet från mellanlagring, baserat på följande tre typer av information:

    - En konfigurerad mappningsregel
    - Härledd juridisk person
    - Härlett leverantörskonto

Om du vill köra en validering, välj **Kontrollera** i visningsprogram för sida-vid-sida. Valideringen utför för närvarande följande kontroller:

- **Obligatorisk check** – Med den här kontrollera valideras de obligatoriska fälten för visningsprogrammet sida vid sida. Användarna kan välja vilka fält som måste vara obligatoriska på sidan **Konfigurationsinställningar**.
- **Konfidenspoäng** – Användarna kan ange varningströskeln och feltröskeln för konfidenspoäng. Den här kontrollen fokuserar på konfidenspoäng från OCR som ligger under dessa tröskelvärden. Fel- eller varningsmeddelanden visas baserat på valideringsresultatet.
- **Juridisk person** – I den här kontrollen valideras att en juridisk person finns i Ekonomi. Om den juridiska personen inte finns i ekonomimiljön misslyckas valideringen.

När visningsprogram för sida-vid-sida används för första gången och användaren väljer **Kontrollera**, körs även processerna för härledning och validering. Om fakturorna är korrekta körs valideringsprocessen när användaren väljer **Slutför granskning**. Den körs också när användaren väljer **Generera leverantörsfaktura**.

Den här processen sker före valideringen och alla varningar eller fel kommer från valideringsprocessen. Varningar och fel loggas i Ekonomi.
