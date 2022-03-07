---
title: Använd den elektroniska faktureringstjänsten för att importera leverantörsfakturor
description: I det här avsnittet finns information om hur du importerar leverantörsfakturor med hjälp av den elektroniska faktureringstjänsten.
author: gionoder
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 434bf1f6a5a727a71592493b85ab166cbeff2f0980c2c968c99973a03f4dc660
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751262"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>Använd den elektroniska faktureringstjänsten för att importera leverantörsfakturor

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Det här ämnet innehåller information som hjälper dig att komma igång med att importera leverantörsfakturor med tjänsten Elektronisk fakturering. Här får du hjälp med konfigurationsstegen i Regulatory Configuration Services (RCS), Dynamics 365 Finance och Dynamics 365 Supply Chain Management som du måste följa för att ta emot elektroniska leverantörsfakturor från leverantörerna.

## <a name="set-up-vendor-invoice-import-in-rcs"></a>Konfigurera leverantörsfakturaimport i RCS
Så här ställer du in import av leverantörsfakturor i RCS:

1. Läs i listan över [allmänt tillgängliga funktioner för elektronisk fakturering](e-invoicing-configuration-rcs.md#generally-available-features).
2. Välj och importera funktion för elektronisk fakturering. För mer information, se [Importera en elektronisk faktureringsfunktion från Microsofts konfigurationsleverantör](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider).
3. Skapa en funktion för elektronisk fakturering för organisation. För mer information, se [Skapa en elektronisk faktureringsfunktion under organisationsleverantör](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider).

## <a name="configure-an-email-account-channel"></a>Konfigurera en e-postkontokanal

Konfigurera en e-postkontokanal om du med hjälp av den elektroniska faktureringsfunktionen importerar elektroniska leverantörsfakturor från bifogade filer som tas emot via e-post.

1. I RCS, välj den funktion för elektronisk fakturering som du har skapat. Se till att du väljer den version som har status **utkast**.
2. På fliken **Inställningar** i rutnätet, välj en funktionsinställning och välj sedan **Redigera**.
3. På fliken **Datakanal** i fältgruppen **Parametrar** väljer du **Serveradress** och anger leverantören för e-postkontot.
4. Välj **serverport** och ange den port som används av e-postkontoprovidern.
5. Välj **Hemlighet för användarnamn** och ange namnet på Key Vault -hemligheten som innehåller ID för e-postkontot.
6. Välj **Hemlighet för användarlösenord** och ange namnet på Key Vault-hemligheten som innehåller lösenord för e-postkontot.
7. Välj **ämnesfilter**. Granska och uppdatera strängen som innehåller standardmeddelandet med e-post om du vill identifiera e-postmeddelandet som innehåller den elektroniska leverantörsfaktura som ska importeras.
8. På fliken **Tillämplighetsregler** kan du granska och uppdatera kriterierna om det behövs. Mer information finns i [Tillämplighetsregler](e-invoicing-configuration-rcs.md#applicability-rules).
9. Markera **Spara** och stäng sedan sidan.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Konfigurera Microsoft SharePoint-kanal

Konfigurera en Microsoft SharePoint-kanal om funktionen Elektronisk fakturering importerar elektroniska leverantörsfakturor från filer i SharePoint-mappar.

1. I RCS, välj den funktion för elektronisk fakturering som du har skapat. Se till att du väljer den **version** som har status **utkast**.
2. På fliken **Inställningar** i rutnätet, välj en funktionsinställning och välj sedan **Redigera**.
3. På fliken **Datakanal** i fältgruppen **Parametrar** väljer du **SharePoint adress** och anger SharePoint URL.
4. Välj **serverport** och ange den port som används av e-postkontoprovidern.
5. Välj **App-Id** och ange namnet på Key Vault-hemligheten som innehåller ID för SharePoint-klient.
6. Välj **Programhemligheten** och ange namnet på Key Vault-hemligheten som innehåller lösenord för SharePoint-klient.
7. Välj **Filfilter**. Granska och uppdatera masken för att filtrera filerna som innehåller den elektroniska leverantörsfakturan som ska importeras.
8. På fliken **Tillämplighetsregler** kan du granska och uppdatera kriterierna om det behövs. Mer information finns i [Tillämplighetsregler](e-invoicing-configuration-rcs.md#applicability-rules).
9. Markera **Spara** och stäng sedan sidan

### <a name="deploy-an-electronic-invoicing-feature"></a>Distribuera den elektroniska faktureringsfunktionen

Om du vill distribuera funktionen Elektronisk fakturering, se [Distribuera funktionen Elektronisk fakturering till servicemiljön](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="set-up-vendor-invoice-import-in-finance-and-supply-chain-management"></a>Konfigurera leverantörsfakturaimport i Finance och Supply Chain Management
Gör stegen i följande två avsnitt om du vill ställa in olika typer av import av leverantörsfaktura.

### <a name="import-vendor-invoices-from-email"></a>Importera leverantörsfakturor från e-post

1. Logga in i Finance eller Supply Chain Management-miljö och kontrollera att du befinner dig i rätt juridisk person.
2. Gå till **Organisationsadministration** > **Inställningar** > **Parametrar för elektroniskt dokument**.
3. På flik **Funktioner**, se till att **NF-e Federal - Brasiliansk elektronisk faktura** är vald.
4. På fliken **Externa kanaler**, i fältgruppen **Kanaler**, välj **Lägg till**.
5. I fältet **Kanalen**, ange **NFe** (namnet på kanalen som anges i konfigurationen av datakanalen för funktionen Elektronisk fakturering i RCS).
6. Ange en beskrivning i fältet **beskrivning**. Välj den juridiska personen i fältet **Företag**.
7. I fältet **Dokumentkontext** väljer du **Skattedokument kontext – Kundfaktura kontextmodell**.
8. I fältgruppen **Importera källor**, välj **Lägg till**.
9. I fältet **Namn**, ange **XmlFile** (namnet för **Bilagefilter** anges i datakanalens konfiguration för funktionen Elektronisk fakturering i RCS).
10. I fältet **Beskrivning** ange en beskrivning och i **Dataenhetens namn**, välj **Mottagna NF-e XML-dokument**.
11. I fältet **Modellmappning**, välj **NF-e-postimport-NF-e-postimport (BR)** och välj **Spara**.
12. På fliken **Elektroniskt dokument**, fältet **Elektroniskt dokument**, välj **Lägg till** och fältet **Tabellnamn**, välj **Mottaget NF-e XML-dokument**.
13. I fältet **Dokumentkontext** väljer du **Fråga skattemässigt dokument sammanhang – Kundfaktura kontext**.
14. I fältet **Modellmappning av Elektronisk dokumentmodell**, välj **Fråga kartläggning - Finansiell dokumentmappning**.
15. Välj **svarstyper** och välj sedan **Ny**.
16. I fältet **svarstyp** anger du **Svar**. I fältet **Överföringsstatus** välj **Schemalagt**.
17. I fältet **Modellmappning** välj **Modellmappning från svarsmeddelande - Importformat för svarsmeddelande**.
18. Markera **Spara** och stäng sedan sidan.

### <a name="import-peppol-electronic-vendor-invoices"></a>PEPPOL importerar elektroniska leverantörsfakturor

1. På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.
2. Välj **kontextmodell för kundfaktura** och skapa en härledd konfiguration.
3. På versionen **Utkast** välj **Designer**.
4. I **Datamodell**, välj **Kundfaktura** och välj **Karta modell till datakälla**.
5. I trädet **Definitioner**, välj **CustomerInvoice** och välj **Designer**.
6. I trädet **Datakällor**, välj **Kontext\_Kanal**. I fältet **Värde**, välj **PEPPOL**. Detta är namnet kanalen, ange namnet på kanalen som anges i konfigurationen av datakanalen för funktionen Elektronisk fakturering i RCS. 
7. Markera **Spara** och stäng sedan sidan.
8. Stäng sidan.
9. Välj **kontextmodellen Kundfaktura** och på snabbfliken **Versioner**, välj **Ändra status** > **Slutförd**.
10. Gå till **Organisationsadministration** > **Inställningar** > **Parametrar för elektroniska dokument** och **Funktioner**, se till att **PEPPOL Globala elektroniska fakturor** är markerad. 
11. På fliken **Externa kanaler**, i fältgruppen **Kanaler**, välj **Lägg till**.
12. I fältet **Kanal**, ange **PEPPOL**. Ange en beskrivning i fältet **beskrivning**.
13. Välj den juridiska personen i fältet **Företag**. I fältet **Dokumentkontext** väljer du **Kundfaktura kontext – Kundfaktura kontextmodell**.
14. Markera **Spara** och stäng sedan sidan.


## <a name="receive-electronic-invoices"></a>Ta emot Elektroniska fakturor
Så här tar du emot elektroniska fakturor:

1. Gå till **Organisationsadministration** > **Periodisk** > **Elektroniska dokument** > **Ta emot elektroniska dokument**.
2. Markera **OK** och stäng sedan sidan.

## <a name="view-receive-logs-for-electronic-invoices"></a>Visa ta emot loggar för elektroniska fakturor

Om du vill visa loggfilerna för elektroniska fakturor går du till **Organisationadministration** > **Periodisk** > **Elektroniska dokument** > **Elektronisk dokumentkvittologg**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
