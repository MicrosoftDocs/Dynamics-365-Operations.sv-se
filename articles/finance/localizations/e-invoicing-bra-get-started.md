---
title: Kom igång med tillägget elektronisk fakturering för Brasilien
description: Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering för Brasilien i Finance och Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: eaf9433ad2d9ccf3d3c5632d0f2d4fe772ff8bde
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592680"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Kom igång med tillägget elektronisk fakturering för Brasilien 

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du kommer igång med tillägget Elektronisk fakturering för Brasilien. Procedurerna i det här avsnittet vägleder dig genom konfigurationsstegen som är landsberoende i Regulatory Configuration Services (RCS) och kompletterar stegen som beskrivs i avsnittet, [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Landsspecifik konfiguration för brasiliansk NF-e (BR) Elektronisk faktureringsfunktion

Om du konfigurerar funktionen för brasiliansk NF-e (BR) elektronisk fakturering måste du slutföra specifika steg. Vissa av parametrarna från konfigurationerna publiceras med standardvärden, så de måste granskas och uppdateras för att bättre passa din verksamhet.

### <a name="prerequisites"></a>Förutsättningar

Innan du slutför proceduren i detta avsnitt, skapa en brasiliansk NF-e (BR) elektronisk faktureringsfunktion för din organisation, som beskrivs i avsnittet **Skapa en elektronisk faktureringsfunktion under din organisationsleverantör** i ämnet [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **globaliseringsfunktion** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Tillägg för elektroniska fakturor**.
2. På sidan **funktioner för tillägget elektronisk fakturering** kontrollerar du att funktionen **Brasiliansk NF-e (BR)** elektronisk fakturering du skapat är vald.
3. I fliken **Versioner** bekräftar du att versionen **Utkast** har valts.
4. På fliken **Inställningar** i rutnätet väljer du **Skicka** och sedan **Redigera**.
5. På fliken **Åtgärder** i fältgruppen **Åtgärder** välj åtgärden **(förhandsversion) logga in xml dokument**.
6. I fältgruppen **Parametrar** väljer du **Certifikatnamn** och i fältet **Värde** anger du namnet på certifikatet som är kopplat till din Key Vault-parameter.
7. På fliken **Åtgärder** i fältgruppen **Åtgärder** välj åtgärden **(förhandsversion) anropa brasilianska SEFAZ-tjänsten**.
8. I fältgruppen **Parametrar**, välj parametern **URL-adress**.
9. I fältet **Värde**, granska och uppdatera URL för de webbtjänster som publiceras av SEFAZ dokumentation för din delstat och välj **Spara.**
10. På fliken **Tillämplighetsregler** i fältgruppen **Inställning av tillämpbarhetsregel**, granska och uppdatera fältkriteriet **Delstat** field efter behov för samma delstat som URL för webbtjänsterna hänvisar till.
11. Markera **Spara** och stäng sedan sidan.
12. För att konfigurera programinställningarna, se [Komma igång med tillägget elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Landsspecifik konfiguration för appinställning för brasiliansk NF-e (BR) Elektronisk faktureringsfunktion

Om du konfigurerar funktionen appinställning för brasiliansk NF-e (BR) elektronisk fakturering måste du slutföra specifika steg. Genomför de här stegen innan du distribuerar din funktion för elektronisk fakturering i din elektroniska faktureringsmiljö.

### <a name="prerequisites"></a>Förutsättningar

Innan du slutför proceduren i detta avsnitt, skapa och initiera appkonfiguration av brasiliansk NF-e (BR) elektronisk faktureringsfunktion som beskrivs i avsnittet **Konfigurera programmets inställningar** i ämnet, [Komma igång med tillägget elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **globaliseringsfunktion** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Tillägg för elektroniska fakturor**.
2. På sidan **funktioner för tillägget elektronisk fakturering** kontrollerar du att funktionen **Brasiliansk NF-e (BR)** elektronisk fakturering är vald.
3. I fliken **Versioner** bekräftar du att versionen **Utkast** har valts.
4. På fliken **Inställningar** väljer du **Programinställningar** och i fältet **Kopplat program** väljer du det program som du vill distribuera till.
5. I fältet **Tabellnamn** verifiera om **skattedokumentets rubrik** är vald.
6. Välj **svarstyper** och välj sedan **Ny**.
7. I fältet **Svarstyp** anger du "Svar" som ett fast värde och i fältet **beskrivning** anger du "Beskrivning".
8. I fältet **Överföringsstatus** välj **Väntande**.
9. I fältet **Modellmappning** välj **Modellmappning från svarsmeddelande** med **(förhandsversion) Importformat för svarsmeddelande** och sedan **Spara**.
10. Välj **Ny** och i fältet **Svarstyp** anger "ResponseData" som ett fast värde och i fältet **Beskrivning** ange "Beskrivning".
11. I fältet **Överföringsstatus** välj **Väntande**.
12. I fältet **Modellmappning** välj **import av svarsdata** med **(förhandsversion) NF-e importformat för svarsdata (BR)** och sedan **Spara**.
13. Om du vill distribuera funktionen Elektronisk fakturering ska du gå till [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Landsspecifik konfiguration för brasiliansk NFS-e ABRASF Curitiba (BR) Elektronisk faktureringsfunktion

Om du konfigurerar funktionen för brasiliansk NFS-e ABRASF Curitiba (BR) elektronisk fakturering måste du slutföra specifika steg. Vissa av parametrarna från konfigurationerna publiceras med standardvärden, så de måste granskas och uppdateras för att bättre passa din verksamhet.

### <a name="prerequisites"></a>Förutsättningar

Innan du slutför proceduren i det här avsnittet ska du skapa en elektronisk faktureringsfunktion för NFS-e ABRASF Curitiba (BR) i din organisation. Det här beskrivs i avsnittet **Konfigurera elektronisk fakturering** i avsnittet [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **globaliseringsfunktion** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Tillägg för elektroniska fakturor**.
2. På sidan **funktioner för tillägget elektronisk fakturering** kontrollerar du att funktionen **Brasiliansk NFS-e ABRASF Curitiba (BR)** elektronisk fakturering du skapat är vald.
3. På fliken **Versioner**, verifiera att versionen **Utkast** markeras och på fliken **Inställningar** i rutnätet, välj **Skicka**.
4. Välj **Redigera** och på fliken **Åtgärder** i fältgruppen **Åtgärder** väljer du den första förekomsten av **(förhandsversion) Signera xml dokument**.
5. I fältgruppen **Parametrar**, välj parametern **Certifikatnamn**.
6. I fältet **Värde**, ange namnet på certifikatet som är kopplat till parametern Key Vault.
7. I fältgruppen **Åtgärder**, välj den andra förekomsten av **(förhandsversion) Signera xml dokument**.
8. I fältgruppen **Parametrar**, välj parametern **Certifikatnamn**.
9. I fältet **Värde**, ange namnet på certifikatet som är kopplat till parametern Key Vault.
10. På fliken **Åtgärder** i fältgruppen **Åtgärder** välj åtgärden **(förhandsversion) anropa brasilianska SEFAZ-tjänsten**.
11. I fältgruppen **Parametrar**, välj parametern **URL-adress**.
12. I fältet **Värde**, granska och uppdatera URL för de webbtjänster som publiceras av skattemyndigheten för staden Curitiba och välj **Spara.**
13. På fliken **Inställningar** i rutnätet väljer du **Fråga** och sedan **Redigera**.
14. På fliken **Åtgärder** i fältgruppen **Åtgärder** välj åtgärden **(förhandsversion) anropa brasilianska SEFAZ-tjänsten**.
15. I fältgruppen **Parametrar**, välj parametern **URL-adress**.
16. I fältet **Värde**, granska och uppdatera URL för de webbtjänster som publiceras av skattemyndigheten för staden Curitiba.
17. Markera **Spara** och stäng sedan sidan.
18. För att konfigurera programinställningarna, se [Komma igång med tillägget elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Landsspecifik konfiguration för appinställningar för brasiliansk NFS-e ABRASF Curitiba (BR) Elektronisk faktureringsfunktion

Om du konfigurerar programinställningarna för brasiliansk NFS-e ABRASF Curitiba (BR) Elektronisk faktureringsfunktion kräver att specifika steg slutförs innan du distribuerar din elektroniska faktureringsfunktion i din tilläggsmiljö för elektronisk fakturering.

### <a name="prerequisites"></a>Förutsättningar

Innan du slutför proceduren i detta avsnitt, skapa och initiera appkonfiguration av brasiliansk NFS-e ABRASF Curitiba (BR) elektronisk faktureringsfunktion som beskrivs i avsnittet **Konfigurera programmets inställningar** i ämnet, [Komma igång med tillägget elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **globaliseringsfunktion** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Tillägg för elektroniska fakturor**.
2. På sidan **funktioner för tillägget elektronisk fakturering** kontrollerar du att funktionen **Brasiliansk NFS-e ABRASF Curitiba (BR)** elektronisk fakturering.
3. På fliken **Versioner**, verifiera att versionen **Utkast** markeras och på fliken **Inställningar** i rutnätet, välj **Programkonfiguration**.
4. I fältet **Anslutet program**, välj det program där du vill distribuera.
5. I fältet **Tabellnamn** verifiera om skattedokumentets rubrik är vald.
6. Välj **svarstyper** och välj sedan **Ny**.
7. I fältet **Svarstyp** anger du "ABRASFCuritibaSubmitResponse" som ett fast värde och i fältet **beskrivning** anger du "Beskrivning".
8. I fältet **Överföringsstatus** välj **Väntande**.
9. I fältet **Modellmappning** välj **import av svarsmeddelande** med **(förhandsversion) NFS-e ABRASF Curitiba import av svarsmeddelande (BR)** och sedan **Spara**.
10. Välj **Ny** och i fältet **Svarstyp** anger "ABRASFCuritibaSubmitResponseData" som ett fast värde och i fältet **Beskrivning** ange "Beskrivning".
11. I fältet **Överföringsstatus** välj **Väntande**.
12. I fältet **Modellmappning** välj **import av svarsdata** med **(förhandsversion) NFS-e ABRASF importformat för svarsdata (BR)** och sedan **Spara**.
13. Välj **Ny** och i fältet **Svarstyp** anger "ABRASFCuritibaInquireResponse" som ett fast värde och i fältet **Beskrivning** ange "Beskrivning".
14. I fältet **Överföringsstatus** välj **Väntande**.
15. I fältet **Modellmappning** välj **import av svarsmeddelande** med **(förhandsversion) NFS-e ABRASF Curitiba import av svarsmeddelande (BR)**.
16. Välj **Spara** och återgå sedan till ämnet [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started.md) för att distribuera den elektroniska faktureringsfunktionen.

## <a name="privacy-notice"></a>Sekretesspolicy
Om du aktiverar funktionerna **NF-e Federal - brasiliansk elektronisk faktura (BR)** och **NFS-e - brasiliansk tjänst (city) elektronisk faktura** kan kräva sändning av begränsad information, inklusive organisationens skatteregistrerings-ID. Denna data kommer att översändas till tredje parts byråer som har tillstånd av skattemyndigheten för att skicka elektroniska fakturor till denna skattemyndighet i det fördefinierade format som krävs för integrering med den offentliga sektorns webbtjänster. Som administratör kan du aktivera eller stänga av funktionerna **NF-e Federal - brasiliansk elektronisk faktura (BR)** och **NFS-e - brasiliansk tjänst (stad) elektronisk faktura**. Följande steg visar hur du gör detta: 

1. Gå till **Organisationsadministration** > **Inställningar** > **Parametrar för elektroniskt dokument**. 
2. På fliken **Funktioner** markerar du den rad som innehåller funktionen **NF-e federal - brasiliansk elektronisk faktura (BR)** eller **NFS-e - brasiliansk tjänst (stad) elektronisk faktura** och välj funktionen. Data som importeras från dessa externa system till denna Dynamics 365 onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132). Mer information finns i sektionerna om sekretessmeddelanden i landsspecifik funktionsdokumentation.

## <a name="additional-resources"></a>Ytterligare resurser

- [Tillägg för elektronisk fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med tjänstadministration för tillägget för elektronisk fakturering](e-invoicing-get-started-service-administration.md)
- [Kom i gång med tillägget för elektronisk fakturering](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
