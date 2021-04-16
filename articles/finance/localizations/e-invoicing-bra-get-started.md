---
title: Kom i gång med elektronisk fakturering för Brasilien
description: Det här avsnittet innehåller information som hjälper dig att komma igång med elektronisk fakturering för Brasilien i Finance och Supply Chain Management.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f8caaa6417365a131da0565cbc4a9f79425d0c7e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840278"
---
# <a name="get-started-with-electronic-invoicing-for-brazil"></a>Kom i gång med elektronisk fakturering för Brasilien 

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information som hjälper dig att komma igång med elektronisk fakturering för Brasilien. Ämnena vägleder dig genom konfigurationsstegen som är landsberoende i Regulatory Configuration Services (RCS) och kompletterar stegen som beskrivs i avsnittet, [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Landsspecifik konfiguration för brasiliansk NF-e (BR) Elektronisk faktureringsfunktion

Vissa av parametrarna från **funktionen Brasiliansk NF-e (BR) elektronisk fakturering** publiceras med standardvärden. Granska värdena om det behövs, uppdatera dem så att de bättre återspeglar verksamhetens behov innan du distribuerar den elektroniska faktureringsfunktionen till tjänstemiljön.

Detta avsnitt kompletterar avsnittet **Landsspecifik konfiguration för funktionen elektronisk fakturering** i ämnet [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **Funktioner** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Elektroniska fakturor**.
2. På sidan **funktioner för elektronisk fakturering** kontrollerar du att funktionen **Brasiliansk NF-e (BR)** elektronisk fakturering du skapat är vald.
3. I fliken **Versioner** bekräftar du att versionen **Utkast** har valts.
4. På fliken **Inställningar** i rutnätet väljer du **Skicka** och sedan **Redigera**.
5. På fliken **Åtgärder** i fältgruppen **Åtgärder** välj åtgärden **(förhandsversion) logga in xml dokument**.
6. I fältgruppen **Parametrar** väljer du **Certifikatnamn** och i fältet **Värde** anger du namnet på certifikatet som är kopplat till din Key Vault-parameter.
7. På fliken **Åtgärder** i fältgruppen **Åtgärder** välj åtgärden **(förhandsversion) anropa brasilianska SEFAZ-tjänsten**.
8. I fältgruppen **Parametrar**, välj parametern **URL-adress**.
9. I fältet **Värde**, granska och uppdatera URL för de webbtjänster som publiceras av SEFAZ dokumentation för din delstat och välj **Spara.**
10. På fliken **Tillämplighetsregler** i fältgruppen **Inställning av tillämpbarhetsregel**, granska och uppdatera fältkriteriet **Delstat** field efter behov för samma delstat som URL för webbtjänsterna hänvisar till.
11. Markera **Spara** och stäng sedan sidan.
12. Om du vill distribuera funktionen Elektronisk fakturering till tjänstmiljön, se [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Landsspecifik konfiguration för appinställning för brasiliansk NF-e (BR) Elektronisk faktureringsfunktion

Genomför de här stegen innan du distribuerar programinställningarna till det anslutna programmet Finance eller Supply Chain Management.

Detta avsnitt kompletterar avsnittet **Landsspecifik konfiguration för programkonfiguration** i ämnet [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **Funktioner** i arbetsytan **Globaliseringsfunktioner**, välj panelen *Elektroniska fakturor*.
2. På sidan **funktioner för elektronisk fakturering** kontrollerar du att funktionen **Brasiliansk NF-e (BR)** elektronisk fakturering är vald.
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
13. För att distribuera appinställningarna till Finance eller Supply Chain ansluten app, se [Kom igång med elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Landsspecifik konfiguration för brasiliansk NFS-e ABRASF Curitiba (BR) Elektronisk faktureringsfunktion

Vissa av parametrarna från **funktionen Brasiliansk NFS-e ABRASF Curitiba (BR) elektronisk fakturering** publiceras med standardvärden. Granska och uppdatera värdena om det behövs, så att de bättre passar verksamhetens behov innan du distribuerar den elektroniska faktureringsfunktionen till tjänstemiljön.

Detta avsnitt kompletterar avsnittet **Landsspecifik konfiguration för funktionen elektronisk fakturering** i ämnet [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **Funktioner** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Elektroniska fakturor**.
2. På sidan **funktioner för elektronisk fakturering** kontrollerar du att funktionen **Brasiliansk NFS-e ABRASF Curitiba (BR)** elektronisk fakturering du skapat är vald.
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
18. Om du vill distribuera funktionen Elektronisk fakturering till tjänstmiljön, se [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Landsspecifik konfiguration för appinställningar för brasiliansk NFS-e ABRASF Curitiba (BR) Elektronisk faktureringsfunktion

Genomför de här stegen innan du distribuerar programinställningarna till det anslutna programmet Finance eller Supply Chain Management.

Detta avsnitt kompletterar avsnittet **Landsspecifik konfiguration för programkonfiguration** i ämnet [Kom igång med Elektronisk fakturering](e-invoicing-get-started.md).

1. I RCS, avsnittet **Funktioner** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Elektroniska fakturor**.
2. På sidan **funktioner för elektronisk fakturering** kontrollerar du att funktionen **Brasiliansk NFS-e ABRASF Curitiba (BR)** elektronisk fakturering.
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
16. Markera **Spara** och stäng sedan sidan.
17. För att distribuera appinställningarna till Finance eller Supply Chain ansluten app, se [Kom igång med elektronisk fakturering](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Sekretesspolicy
Om du aktiverar funktionerna **NF-e Federal - brasiliansk elektronisk faktura (BR)** och **NFS-e - brasiliansk tjänst (city) elektronisk faktura** kan kräva sändning av begränsad information, inklusive organisationens skatteregistrerings-ID. Denna data kommer att översändas till tredje parts byråer som har tillstånd av skattemyndigheten för att skicka elektroniska fakturor till denna skattemyndighet i det fördefinierade format som krävs för integrering med den offentliga sektorns webbtjänster. Som administratör kan du aktivera eller stänga av funktionerna **NF-e Federal - brasiliansk elektronisk faktura (BR)** och **NFS-e - brasiliansk tjänst (stad) elektronisk faktura**. Följande steg visar hur du gör detta: 

1. Gå till **Organisationsadministration** > **Inställningar** > **Parametrar för elektroniskt dokument**. 
2. På fliken **Funktioner** markerar du den rad som innehåller funktionen **NF-e federal - brasiliansk elektronisk faktura (BR)** eller **NFS-e - brasiliansk tjänst (stad) elektronisk faktura** och välj funktionen. Data som importeras från dessa externa system till denna Dynamics 365 onlinetjänst omfattas av vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=512132). Mer information finns i sektionerna om sekretessmeddelanden i landsspecifik funktionsdokumentation.

## <a name="additional-resources"></a>Ytterligare resurser

- [Elektronisk fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med tjänstadministration för elektronisk fakturering](e-invoicing-get-started-service-administration.md)
- [Kom i gång med elektronisk fakturering](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
