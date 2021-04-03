---
title: Kom i gång med tillägget för elektronisk fakturering för Egypten
description: Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering för Egypten i Finance och Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 02/26/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 68ee08226f440e850a080600dbf5e16768b45e43
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592608"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-egypt"></a>Kom i gång med tillägget för elektronisk fakturering för Egypten

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering för Egypten. Ämnena vägleder dig genom konfigurationsstegen som är landsberoende i Regulatory Configuration Services (RCS) och kompletterar stegen som beskrivs i avsnittet, [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Landsspecifik konfiguration för egyptisk elektronisk faktura (EG) Elektronisk faktureringsfunktion

För att konfigurera egyptisk elektronisk fakturafunktion (EG), finns det några steg att slutföra. Vissa av parametrarna från konfigurationerna publiceras med standardvärden, så de måste granskas och uppdateras för att bättre passa din verksamhet.

### <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra denna procedur i detta avsnitt måste du:

- Skapa en digital certifikatshemlighet, som beskrivs i avsnittet **Skapa digitalt certifikatshemlighet** i [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started-service-administration.md). För teständamål tillhandahåller den egyptiska skattemyndigheten specifika digitala testcertifikat som endast får användas under test- och lösningsvalideringsfaser. För mer information, besök den egyptiska skattemyndighetens webbplats med länken i [Egyptisk e-fakturering SDK](https://sdk.sit.invoicing.eta.gov.eg/faq/).
- Skapa en egyptisk elektronisk faktura (EG) elektronisk faktureringsfunktion för din organisation, som beskrivs i avsnittet **Skapa en elektronisk faktureringsfunktion under din organisationsleverantör** i ämnet [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **globaliseringsfunktion** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Tillägg för elektroniska fakturor**.
2. På sidan **funktioner för tillägget elektronisk fakturering** kontrollerar du att funktionen **Egyptisk elektronisk faktura (EG)** elektronisk fakturering du skapat är vald.
3. I fliken **Versioner** bekräftar du att versionen **Utkast** har valts.
4. På fliken **Inställningar** i rutnätet väljer du funktionsinställningen **Försäljningsfaktura**.
5. Välj **Redigera** och på fliken **Åtgärder** i fältgruppen **Åtgärder**, välj **Signera json-dokument för egyptisk skattemyndighet**.
6. I fältgruppen **Parametrar**, välj parameter, **Certifikatnamn** och välj namnet på det digitala certifikat som skapats för användning med funktionen Elektronisk fakturering.
7. I fältgruppen **Åtgärder**, välj **Integrera med egyptisk ETA-tjänst**. Upprepa det här steget för de två förekomsterna av åtgärden.
8. I fältgruppen **Parametrar**, välj **Webbtjänst-URL** och **Inloggningstjänst-URL** och om nödvändigt granska URL-parametrarna. Gå till den egyptiska skattemyndighetens webbplats för att få URL för testning och produktion med hjälp av länken i [Egyptisk e-fakturering SDK](https://sdk.sit.invoicing.eta.gov.eg/faq/).
9. Markera **Spara** och stäng sedan sidan.
10. För att konfigurera programinställningarna, se [Komma igång med tillägget elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-the-application-setup-for-the-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Landsspecifik konfiguration av appinställningen för egyptisk elektronisk fakturafunktion (EG)

Konfigurationen av appinställningen för **Egyptisk elektronisk faktura (EG)** elektronisk faktureringsfunktion kräver att specifika steg utförs. Du måste utföra dessa steg innan du distribuerar din funktion för elektronisk fakturering i din elektroniska faktureringsmiljö.

### <a name="prerequisites"></a>Förutsättningar

Innan du slutför proceduren i detta avsnitt, skapa och initiera en **Egyptisk elektronisk faktura (EG)** Elektronisk faktureringsfunktion för att konfigurera appinställningen för **Egyptisk elektronisk faktura (EG)** Elektronisk faktureringsfunktion, som beskrivs i avsnittet **Konfigurera appinställningarna** i ämnet, [Kom i gång med tillägget för elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **globaliseringsfunktion** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Tillägg för elektroniska fakturor**.
2. På sidan **funktioner för tillägget elektronisk fakturering** kontrollerar du att funktionen **Egyptisk elektronisk faktura (EG)** elektronisk fakturering är vald.
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
14. Om du vill distribuera funktionen Elektronisk fakturering ska du gå till [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Sekretesspolicy

Om du aktiverar funktionen **Egyptisk elektronisk faktura (EG)** kan det krävas att begränsade data skickas, vilket inkluderar organisationens momsregistrerings-ID. Denna data kommer att översändas till tredje parts byråer som har tillstånd av skattemyndigheten för att skicka elektroniska fakturor till denna skattemyndighet i det fördefinierade format som krävs för integrering med den offentliga sektorns webbtjänster. En administratör kan aktivera och inaktivera funktionen genom att gå till **Organisationsadministration** > **Inställningar** > **Parametrar för elektroniskt dokument**. Välj fliken **Funktioner**, markera den rad som innehåller funktionerna **Egyptisk elektronisk faktura (EG)** och välj sedan lämpligt alternativ. Data som importeras från dessa externa system till denna Dynamics 365 onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132). Mer information finns i sektionerna om sekretessmeddelanden i landsspecifik funktionsdokumentation.

## <a name="additional-resources"></a>Ytterligare resurser

- [Tillägg för elektronisk fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med tjänstadministration för tillägget för elektronisk fakturering](e-invoicing-get-started-service-administration.md)
- [Kom i gång med tillägget för elektronisk fakturering](e-invoicing-get-started.md)
- [Elektroniska kundfakturor i Egypten](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
