---
title: Kom i gång med elektronisk fakturering för Egypten
description: Det här avsnittet innehåller information som hjälper dig att komma igång med elektronisk fakturering för Egypten i Finance och Supply Chain Management.
author: gionoder
ms.date: 04/20/2021
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
ms.openlocfilehash: 03ccc18d4c767dbb2a314e2eb1076b1c6e9019e991c6de3fc80be65d765fdd36
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758810"
---
# <a name="get-started-with-electronic-invoicing-for-egypt"></a>Kom i gång med elektronisk fakturering för Egypten

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information som hjälper dig att komma igång med elektronisk fakturering för Egypten. Ämnena vägleder dig genom konfigurationsstegen som är landsberoende i Regulatory Configuration Services (RCS) och kompletterar stegen som beskrivs i [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Landsspecifik konfiguration för egyptisk elektronisk faktura (EG) Elektronisk faktureringsfunktion

Vissa av parametrarna från **funktionen Egyptisk elektronisk faktura (EG)** publiceras med standardvärden. Granska värdena om det behövs, uppdatera dem så att de bättre återspeglar verksamhetens behov innan du distribuerar den elektroniska faktureringsfunktionen till tjänstemiljön.

Detta avsnitt kompletterar avsnittet **Landsspecifik konfiguration för funktionen elektronisk fakturering** i ämnet [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

### <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra denna procedur i detta avsnitt måste du:

- Skapa en digital certifikatshemlighet, som beskrivs i avsnittet **Skapa digitalt certifikatshemlighet** i [Kom igång med Elektronisk fakturering](e-invoicing-get-started-service-administration.md). För teständamål tillhandahåller den egyptiska skattemyndigheten specifika digitala testcertifikat som endast får användas under test- och lösningsvalideringsfaser. För mer information, besök den egyptiska skattemyndighetens webbplats med länken i [Egyptisk e-fakturering SDK](https://sdk.sit.invoicing.eta.gov.eg/faq/).

1. I RCS, avsnittet **Funktioner** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Elektroniska fakturor**.
2. På sidan **funktioner för elektronisk fakturering** kontrollerar du att funktionen **Egyptisk elektronisk faktura (EG)** elektronisk fakturering du skapat är vald.
3. I fliken **Versioner** bekräftar du att versionen **Utkast** har valts.
4. På fliken **Inställningar** i rutnätet väljer du funktionsinställningen **Försäljningsfaktura**.
5. Välj **Redigera** och på fliken **Åtgärder** i fältgruppen **Åtgärder**, välj **Signera json-dokument för egyptisk skattemyndighet**.
6. I fältgruppen **Parametrar**, välj parameter, **Certifikatnamn** och välj namnet på det digitala certifikat som skapats för användning med funktionen Elektronisk fakturering.
7. I fältgruppen **Åtgärder**, välj **Integrera med egyptisk ETA-tjänst**. Upprepa det här steget för de två förekomsterna av åtgärden.
8. I fältgruppen **Parametrar**, välj **Webbtjänst-URL** och **Inloggningstjänst-URL** och om nödvändigt granska URL-parametrarna. Gå till den egyptiska skattemyndighetens webbplats för att få URL för testning och produktion med hjälp av länken i [Egyptisk e-fakturering SDK](https://sdk.sit.invoicing.eta.gov.eg/faq/).
9. Markera **Spara** och stäng sedan sidan.
10. Om du vill distribuera funktionen Elektronisk fakturering till tjänstmiljön, se [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-the-application-setup-for-the-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Landsspecifik konfiguration av appinställningen för egyptisk elektronisk fakturafunktion (EG)

Genomför de här stegen innan du distribuerar programinställningarna till det anslutna programmet Finance eller Supply Chain Management.

Detta avsnitt kompletterar avsnittet **Landsspecifik konfiguration för programkonfiguration** i ämnet [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **Funktioner** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Elektroniska fakturor**.
2. På sidan **funktioner för elektronisk fakturering** kontrollerar du att funktionen **Egyptisk elektronisk faktura (EG)** elektronisk fakturering är vald.
3. I fliken **Versioner** bekräftar du att versionen **Utkast** har valts.
4. På fliken **Inställningar** väljer du **Programinställningar** och i fältet **Kopplat program** väljer du det program som du vill distribuera till.
5. I fältet **Tabellnamn**, verifiera att kundfakturajournalen är vald.
6. Välj **svarstyper** och välj sedan **Ny**.
7. I fältet **Svarstyp** anger du "Svar" och i fältet **beskrivning** anger du "Beskrivning".
8. I fältet **Överföringsstatus** välj **Väntande**.
9. I fältet **Modellmappning** välj **Modellmappning från svarsmeddelande** med **(förhandsversion) Importformat för svarsmeddelande** och sedan **Spara**.
10. Markera **Ny** och sedan, i fältet **Svarstyp**, markerar du ResponseData som ett fast värde. Ange en beskrivning i fältet **beskrivning**.
11. I fältet **Överföringsstatus** välj **Väntande**.
12. I fältet **Namn på dataenhet**, välj **Försäljningsfakturahuvuden V2**.
13. I fältet **Modellmappning** välj **Egypten import av svarsdata** med **(förhandsversion) Egypten import för svarsdata** och sedan **Spara**.
14. För att distribuera appinställningarna till Finance eller Supply Chain Management ansluten app, se [Kom igång med elektronisk fakturering](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Sekretesspolicy

Om du aktiverar funktionen **Egyptisk elektronisk faktura (EG)** kan det krävas att begränsade data skickas, vilket inkluderar organisationens momsregistrerings-ID. Denna data kommer att översändas till tredje parts byråer som har tillstånd av skattemyndigheten för att skicka elektroniska fakturor till denna skattemyndighet i det fördefinierade format som krävs för integrering med den offentliga sektorns webbtjänster. En administratör kan aktivera och inaktivera funktionen genom att gå till **Organisationsadministration** > **Inställningar** > **Parametrar för elektroniskt dokument**. Välj fliken **Funktioner**, markera den rad som innehåller funktionerna **Egyptisk elektronisk faktura (EG)** och välj sedan lämpligt alternativ. Data som importeras från dessa externa system till denna Dynamics 365 onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132). Mer information finns i sektionerna om sekretessmeddelanden i landsspecifik funktionsdokumentation.

## <a name="additional-resources"></a>Ytterligare resurser

- [Elektronisk fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med tjänstadministration för elektronisk fakturering](e-invoicing-get-started-service-administration.md)
- [Kom i gång med elektronisk fakturering](e-invoicing-get-started.md)
- [Elektroniska kundfakturor i Egypten](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
