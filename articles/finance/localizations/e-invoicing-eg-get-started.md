---
title: e-fakturering för Egypten
description: Den här artikeln innehåller information som hjälper dig att komma igång med e-fakturering för Egypten i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 02/09/2022
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
ms.openlocfilehash: c2a46ef938c5dee62c0d0acd1648584df344c81a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904424"
---
# <a name="electronic-invoicing-for-egypt"></a>e-fakturering för Egypten

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information som hjälper dig att komma igång med e-fakturering för Egypten. Den guidar dig genom de konfigurationssteg som är landsberoende i RCS (Regulatory Configuration Service). Dessa steg kompletterar stegen som beskrivs i [Konfigurera e-fakturering](e-invoicing-set-up-overview.md).

## <a name="prerequisites"></a>Förutsättningar

Innan du kan inleda procedurerna i detta ämne måste följande förutsättningar finnas på plats:

- Bekanta dig med e-fakturering enligt beskrivningen i [Översikt över e-fakturering](e-invoicing-service-overview.md).
- Registrera dig för RCS och konfigurera e-fakturering. Mer information finns i följande avsnitt:

    - [Översikt över registrering och installation av tjänsten för e-fakturering](e-invoicing-sign-up-install.md)
    - [Konfigurera Azure-resurser för e-fakturering](e-invoicing-set-up-azure-resources.md)
    - [Installera tillägget för mikrotjänster i Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    
- Aktivera integreringen mellan ditt Microsoft Dynamics 365 Finance eller din Dynamics 365 Supply Chain Management-program och e-faktureringstjänsten enligt beskrivningen i [Aktivera och ställ in integrering med e-fakturering](e-invoicing-activate-setup-integration.md).
- Skapa en digital certifikathemlighet i Azure Key Vault och ställ in den på det sätt som beskrivs i [Kundcertifikat och hemligheter.](e-invoicing-customer-certificates-secrets.md). För teständamål tillhandahåller den egyptiska skattemyndigheten specifika digitala testcertifikat som endast får användas under test- och lösningsvalideringsfaser. För mer information, besök den egyptiska skattemyndighetens webbplats via länken som tillhandahålls i [Egyptisk e-fakturering SDK](https://sdk.invoicing.eta.gov.eg/faq/).

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-feature"></a>Landsspecifik konfiguration för funktionen för egyptisk e-faktura (EG)

Vissa av parametrarna från funktionen för **Egyptisk e-faktura (EG)** publiceras med standardvärden. Innan du distribuerar funktionen för e-fakturering till tjänstemiljön ska du granska standardvärdena och uppdatera dem så att de ger en bättre bild av dina affärsåtgärder.

1. Importera den senaste versionen av globaliseringsfunktionen **e-faktura för Egypten (EG)** enligt beskrivet i [Importera funktioner från den globala databasen](e-invoicing-import-feature-global-repository.md).
2. Skapa en kopia av den importerade globaliseringsfunktionen och välj din konfigurationsleverantör för den, enligt beskrivningen i [Skapa en globaliseringsfunktion](e-invoicing-create-new-globalization-feature.md).
3. I fliken **Versioner** bekräftar du att versionen **Utkast** har valts.
4. På fliken **Inställningar** i rutnätet väljer du funktionsinställningen **Härledd försäljningsfaktura**.
5. Välj **Redigera**.
6. På fliken **Bearbetningspipeline**, i avsnittet **Bearbetningspipeline**, väljer du **Signera json-dokument för den egyptiska skattemyndigheten**.
7. I avsnittet **Parametrar** väljer du **Certifikatsnamn** och sedan namnet på det digitala certifikat som du skapat.
8. I avsnittet **Bearbetningspipeline** väljer du **Integrera med egyptisk ETA-tjänst**. Upprepa det här steget för de två förekomsterna av åtgärden.
9. I avsnittet **Parametrar** väljer du **URL för webbtjänst** och **URL för inloggningstjänst**. Granska sedan URL-parametrarna. För att få en URL till test och produktion, gå till den egyptiska skattemyndighetens webbplats via länken i [SDK för egyptisk e-fakturering](https://sdk.invoicing.eta.gov.eg/faq/).
10. Markera **Spara** och stäng sedan sidan.
11. Upprepa steg 4 till och med 10 för inställningarna av funktionen **Härledd projektfaktura**.

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-application-setup"></a>Landsspecifik konfiguration för funktionen för ansökningskonfiguration egyptisk e-faktura (EG)

Det finns parametrar som måste ställas in i din Ekonomi- eller Supply Chain Management-miljö. Du kan slutföra inställningen på endera av två ställen:

- Direkt i din instans för Finance eller Supply Chain Management. För mer information, se [Konfigurera parametrar för e-fakturering](e-invoicing-set-up-parameters.md).
- I RCS. Inom området för inställningar av funktionen för e-fakturering kan du definiera alla parametrar och sedan distribuera dem direkt till din Ekonomi- eller Supply Chain Management-miljö när du distribuerar e-faktureringsfunktionen.

Parametrarna är desamma oavsett alternativ. Om du ställer in din första funktion i e-faktureringstjänsten rekommenderar vi att du följer dessa steg för att ställa in parametrarna i RCS och sedan distribuerar dem till det anslutna programmet.

> [!NOTE]
> Vissa versioner av e-faktureringsfunktioner kan innehålla en fördefinierad uppsättning programspecifika parametrar för Ekonomi eller Supply Chain Management. I så fall bör du kontrollera att dina data är korrekta. I annat fall ställer du in parametrarna manuellt.

1. Leta reda på kopian av globaliseringsfunktionen för **e-faktura för Egypten (EG)** som du har skapat.
2. I fliken **Versioner** bekräftar du att versionen **Utkast** har valts.
3. På fliken **Konfigurationer** väljer du **Programkonfiguration**.
4. I fältet **Anslutna program** väljer du det program där du vill distribuera parametrarna.
5. På sidan **Elektroniska dokumenttyper** väljer du **Lägg till** för att skapa en post.
6. I fältet **Tabellnamn** lägger du till **CustInvoiceJour**.
7. I fältet **Kontext** lägger du till en referens till mappningsnamnet **Kontext för kundfaktura**. Konfigurationen är **Kontextmodell för kundfaktura**.
8. I fältet **Mappning av elektroniskt dokument** lägger du till en referens till mappningsnamnet **Kundfaktura**. Konfigurationen är **Mappning av fakturamodell**.
9. Välj **Spara**.
10. På sidan **Svarstyper** väljer du **Lägg till**.
11. I fältet **svarstyp** anger du **Svar**.
12. I fältet **Beskrivning** anger du **Bearbeta respons**.
13. I fältet **Överföringsstatus** välj **Väntande**.
14. I fältet **Modellmappning** väljer du **Import av svarsmeddelande**. Konfigurationen är **Import av egyptiska svarsmeddelanden (EG)**.
15. Välj **Spara**.
16. Markera **Lägg till**.
17. I fältet **Svarstyp** anger du **ResponseData**.
18. I fältet **Beskrivning** anger du **Bearbeta responsdata**.
19. I fältet **Överföringsstatus** välj **Väntande**.
20. I fältet **Namn på dataenhet** väljer du **SalesInvoiceHeaderV2Entity**.
21. I fältet **Modellmappning** väljer du **Response data import**. Konfigurationen är **Importformat för egyptiska svarsdata (EG)**.
22. Markera **Spara** och stäng sedan sidan.
23. Stäng sidan.

Information om hur du distribuerar en funktion till tjänstemiljön och en programinställning i det anslutna Ekonomi- eller Supply Chain Management-programmet finns i [Slutför, publicera och distribuera en globaliseringsfunktion.](e-invoicing-complete-publish-deploy-globalization-feature.md)

## <a name="privacy-notice"></a>Sekretesspolicy

Om du vill aktivera funktionen för **e-faktura i Egypten** måste kanske begränsade data skickas. Dessa data inkluderar företagets momsregistrerings-ID. Datan kommer att översändas till tredjeparts representanter som har auktoriserats av skattemyndigheten att skicka e-fakturor till denna skattemyndighet i det fördefinierade format som krävs för integrering med den myndinghetens webbtjänst. En administratör kan aktivera och inaktivera funktionen genom att gå till **Organisationsadministration** \> **Inställningar** \> **Parametrar för elektroniskt dokument**. Välj fliken **Funktioner**, markera den rad som innehåller funktionerna **Egyptisk e-faktura (EG)** och välj sedan lämpligt alternativ. Data som importeras från dessa externa system till denna Dynamics 365-onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132). Mer information finns i avsnittet "Sekretessmeddela" i landsspecifik funktionsdokumentation.

## <a name="additional-resources"></a>Ytterligare resurser

- [E-fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med tjänstadministration för e-fakturering](e-invoicing-get-started-service-administration.md)
- [Kom i gång med e-fakturering](e-invoicing-get-started.md)
- [Elektroniska kundfakturor i Egypten](emea-egy-e-invoices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
