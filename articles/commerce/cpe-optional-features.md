---
title: Konfigurera valfria funktioner för en bedömningsmiljö för Dynamics 365 Commerce
description: Detta ämne förklarar hur du konfigurerar valfria funktioner för bedömningsmiljö för Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6639de250557ce9a25fc2cde3807abf64b0ddc18
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993460"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a>Konfigurera valfria funktioner för en bedömningsmiljö för Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Detta ämne förklarar hur du konfigurerar valfria funktioner för bedömningsmiljö för Microsoft Dynamics 365 Commerce.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste uppfyllas om du vill utvärdera e-postfunktionerna för transaktion:

- Du kan ha en tillgänglig e-postserver (Simple Mail Transfer Protocol \[SMTP\]- server) som kan användas från Microsoft Azure-prenumeration där du tillhandahåller bedömningsmiljö.
- Du har serverns fullt kvalificerade domännamn (FQDN)-/IP-nummer, SMTP-portnummer och autentiseringsinformation.

## <a name="configure-the-image-back-end"></a>Konfigurera bildserver

### <a name="find-your-media-base-url"></a>Hitta din mediebas-URL

> [!NOTE]
> Innan du kan slutföra den här proceduren måste du slutföra stegen i [konfigurera din webbplats i Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).

1. Logga in på verktyget Commerce webbplatsskaparen med hjälp av den URL som du antecknade när du initierade näthandel under etableringen (se [initiera näthandel](provisioning-guide.md#initialize-e-commerce)).
1. Öppna webbplatsen **Fabrikam**.
1. I menyn till vänster, välj **Mediebibliotek**.
1. Markera en enskild bildtillgång.
1. Hitta egenskapen i egenskapsinspektören till höger **offentlig URL**. Värdet är en URL. Här är ett exempel:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.

1. Ersätt den sista identifieraren i URL:en (**MA1nQC** i exemplet ovan) med strängen **search?fileName=**. Här är vad exempel-URL ser ut efter denna ändring görs:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    Den här URL:en är din mediebas-URL. Anteckna det.

### <a name="update-the-media-base-url"></a>Uppdatera mediebas-URL

1. Logga in på Commerce-administration.
1. Med hjälp av menyn till vänster, gå till **Moduler \> Retail och Commerce \> Kanalinställning \> Kanalprofiler**.
1. Välj **Redigera**.
1. Under **Profilegenskaper**, ersätt värdet för egenskapen **Medieserverbas-URL** med den mediebas-URL du skapade tidigare.
1. Välj kanalen med namnet **scXXXXXXXXX**.
1. Under **Profilegenskaper**, klicka på **Lägg till**.
1. För egenskapen som har lagts till väljer du **medieserverns bas-URL** som egenskapsnyckel. Ange den mediebas-URL som du skapade tidigare som egenskapsvärde.
1. Välj **Spara**.

## <a name="configure-and-test-the-email-server"></a>Konfigurera och testa e-postserver

> [!NOTE]
> SMTP-servern eller e-posttjänsten som du anger här måste vara tillgänglig från den Azure-prenumeration du använder för miljön.

1. Logga in på Commerce-administration.
1. Använd menyn till vänster, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> Parametrar \> E-postparametrar**.
1. På fliken **SMTP-inställningar** i fältet **utgående e-postserver** anger du FQDN- eller IP-adressen för SMTP-servern eller e-posttjänsten.
1. Ange **SMTP-portnummer** anger du portnumret. (Om du inte använder Secure Sockets Layer \[SSL\], är standardportnumret **25**.)
1. Om autentisering krävs anger du värden i fälten **användarnamn** och **lösenord**.
1. Välj **Spara**.
1. Välj **uppdatera**.
1. På fliken **testa e-post** i fältet **e-postleverantör** väljer du **SMTP**.
1. I fältet **Skicka till** ange e-postadressen där du vill att testmeddelandet ska levereras.
1. Välj **Skicka testmeddelande**.

## <a name="configure-email-templates"></a>Konfigurera e-postmallar

För varje transaktionshändelse som du vill skicka e-post till måste du uppdatera e-postmallen med en giltig e-postadress till avsändaren.

1. Logga in på Commerce-administration.
1. Använd menyn till vänster, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar**.
1. Välj **Visa lista**.
1. Följ dessa steg i listan för varje mall:

    1. I fälten **avsändarens e-postadress**, ange avsändarens e-postadress.
    1. Valfritt: I fältet **Avsändarens namn** ange namnet som ska användas som avsändarnamn.

1. Välj **Spara**.

## <a name="customize-email-templates"></a>Anpassa e-postmallar

Du kanske vill anpassa e-postmallarna så att de använder olika bilder. Eller så kanske du vill uppdatera länkarna i mallarna så att de går till din bedömningsmiljö. Den här proceduren förklarar hur du hämtar standardmallarna, anpassar dem och uppdaterar mallarna i systemet.

1. Med hjälp av en webbläsare, hämta [Microsoft Dynamics 365 Commerce utvärdering av standard e-postmallar .zip-fil](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) till den lokala datorn. Den här filen innehåller följande HTML-dokument:

    - Orderbekräftelsemall
    - Utfärda presentkortsmall
    - Ny ordermall
    - Förpackningsordermall
    - Hämta förpackningsordermall

1. Anpassa mallarna med hjälp av en text- eller HTML-redigerare. Se listan över [token som stöds](#supported-tokens-in-the-email-template) senare i det här avsnittet.
1. Logga in på Commerce.
1. Med hjälp av menyn till vänster, gå till **Moduler \> Organisationsadministration \> Inställning \> E-postmall för organisation**.
1. Expandera listan till vänster om du vill se alla mallar.
1. Gör så här för varje mall som du vill anpassa:

    1. Välj mallen i listan.
    1. Under **Innehåll i e-postmeddelande**, välj lämplig språkversion från listan. (Standardspråk är **en-us**.)
    1. Under **Innehåll i e-postmeddelande**, välj **redigera**. Fönstret **överför e-postmall** visas.
    1. Välj **bläddra** och leta reda på HTML-filen med det anpassade innehållet.
    1. Välj **överför**. Mallen överförs till systemet och en förhandsversion visas.
    1. Välj **OK**.
    1. Valfritt: Anpassa egenskapen **ämne** för mallen.
    1. Välj **Spara**.

### <a name="supported-tokens-in-the-email-template"></a>Variabler som stöds i e-postmallen

När e-postmeddelandet återges ersätts dessa tokens med faktiska värden som gäller för kunden och kundens beställning.

#### <a name="sales-order"></a>Försäljningsorder

Följande token gäller för den övergripande försäljningsordern.

| Namn på token | Token  |
|-------------------|-------|
| Ordernummer      | %salesid% |
| Kundnamn   | %customername% |
| Leveransadress  | %deliveryaddress% |
| Faktureringsadress   | %customeraddress% |
| Orderdatum        | %shipdate% |
| Leveranssätt     | %modeofdelivery% |
| Rabatt          | %discount% |
| Moms         | %tax% |
| Ordersumma       | %total% |

#### <a name="sales-line"></a>Försäljningsrad

Följande token ersätts med värden för varje produkt i ordningen.

> [!NOTE]
> Placera token **produktlista – start** i början av HTML-blocket som upprepas för varje produkt och placera token **produktlista – slut** i slutet av blocket.

| Namn på token      | Token |
|------------------------|-------|
| Produktlista – start   | \<!--%tablebegin.salesline% --\> |
| Produktlista – slut     | \<!--%tableend.salesline%--\> |
| Produktnamn           | %lineproductname% |
| beskrivning            | %lineproductdescription% |
| Antal               | %linequantity% |
| Pris för radenhet        | %lineprice% (verifiera) |
| totalbelopp för radartikel        | %linenetamount% |
| radrabatt          | %linediscount% |
| Transportdatum              | %lineshipdate% |
| Anskaffningsmetod     | %linedeliverymode% |
| leveransadress       | %linedeliveryaddress% |
| Försäljningsenhet för raden | %lineunit% |

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Commerce bedömningsmiljö – översikt](cpe-overview.md)

[Etablera en Dynamics 365 Commerce bedömningsmiljön](provisioning-guide.md)

[Konfigurera en Dynamics 365 Commerce bedömningsmiljö](cpe-post-provisioning.md)

[Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö](cpe-bopis.md)

[Dynamics 365 Commerce bedömningsmiljö – vanliga frågor](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portal](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce webbplatsen](https://aka.ms/Dynamics365CommerceWebsite)
