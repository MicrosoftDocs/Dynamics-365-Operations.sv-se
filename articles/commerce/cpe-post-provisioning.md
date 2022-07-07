---
title: Konfigurera en sandbox-miljö för Dynamics 365 Commerce
description: Denna artikel förklarar hur du konfigurerar en sandbox-miljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.
author: psimolin
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 259a580981003f135e234f66e9e93ceb18605412
ms.sourcegitcommit: 252cb41c3029b623354698463f7b44a29fd9f184
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013119"
---
# <a name="configure-a-dynamics-365-commerce-sandbox-environment"></a>Konfigurera en sandbox-miljö för Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Denna artikel förklarar hur du konfigurerar en sandbox-miljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.

Slutför procedurerna i denna artikel först när sandbox-miljön för Commerce har etablerats. Information om hur du konfigurerar etablerar sandbox-miljö för Commerce, se [Etablera en sandbox-miljö för Commerce](provisioning-guide.md).

När din sandbox-miljö för Commerce har etablerats måste ytterligare konfigurationssteg för efter etableringen slutföras innan du kan börja utvärdera miljön. Om du vill utföra dessa steg måste du använda Microsoft Dynamics Lifecycle Services (LCS) och Dynamics 365 Commerce.

## <a name="before-you-start"></a>Innan du börjar

1. Logga in på [LCS-portal](https://lcs.dynamics.com).
1. Gå till ditt projekt.
1. Välj din miljö i listan.
1. Välj i miljöinformation till höger **Logga in i miljön**. Du kommer att skickas till Commerce headquarters.
1. Kontrollera att **USRT** juridisk person har valts i övre högra hörnet. Den här proceduren refererar till den juridiska personen i demodata.
1. Gå till **Handelsparametrar \> Konfigurationsparametrar** och se till att det finns en post för **ProductSearch.UseAzureSearch** och att värdet är **true**. Om den här posten saknas lägger du till den och ställer in värdet till **sant**.
1. Gå till **Butik och handel \> Administrationsinställning \> Schemaläggare för handel \> Initiera schemaläggare för handel**. På den utfällbara menyn **Initiera schemaläggare för handel** se till att alternativet **Ta bort befintligt konfiguration** anges till **Ja** och välj **OK**.
1. Om butiks- och e-handelskanalerna ska fungera korrekt måste de läggas till i enheten för Commerce Scale Unit. Gå till **Butik och handel \> Administrationsinställning \> Handelsschemaläggare \> Kanaldatabas**, och välj sedan i den vänstra rutan Commerce Scale Unit. På snabbfliken **Butikskanal**, lägg till kanalerna **AW-onlinebutik**, **AW Business-onlinebutik** och **Fabrikam utökade online-butik** om du planerar att använda dessa ehandelskanaler. Alternativt kan du också lägga till detaljhandelsbutiker om du ska använda kassa (till exempel **Seattle**, **San Francisco** och **San Jose**).
1. Om du vill vara säker på att alla ändringar är synkroniserade med kanaldatabasen väljer du **kanaldatabasen \> Fullständig datasynkronisering** för Commerce Scale Unit.

Under åtgärderna efter etablering i Commerce headquarters, se till att den juridiska personen **USRT** alltid är vald.

## <a name="configure-the-point-of-sale"></a>Konfigurera POS

### <a name="associate-a-worker-with-your-identity"></a>Associera medarbetare med din identitet

Om du vill associera en anställd med din identitet, följ dessa steg i Commerce headquarters.

1. Använd menyn till vänster för att gå till **moduler \> Retail och Commerce \> anställda \> medarbetare**.
1. Hitta och markera följande post: **000713 – Andrew Collette** i listan. Det här exempelanvändaren associeras med den San Francisco-butik som ska användas i nästa avsnitt.
1. I åtgärdsfönstret, välj **Commerce**.
1. Välj **Associera befintlig identitet**.
1. I fältet **E-post** (till höger om **Sök via e-post**), skriv din e-postadress.
1. Välj **Sök**.
1. Markera posten med ditt namn.
1. Välj **OK**.
1. Välj **Spara**.

### <a name="activate-cloud-pos"></a>Aktivera molnbaserad kassa

Om du vill aktivera Cloud POS i LCS, följ dessa steg.

1. På huvudmenyn väljer du miljön **Molnstyrda miljöer**.
1. Välj din miljö i listan.
1. Välj i miljöinformation till höger **Logga in i molnbaserad kassa**.
1. Välj **Nästa** om du vill öppna dialogrutan **innan du startar**.
1. Lämna fältet **Server URL** tomt. Välj **Nästa**.
1. Logga in med ditt Microsoft Azure Active Directory (Azure AD)-konto.
1. Under **Butiksnamn**, välj **San Francisco** och välj sedan **Nästa**.
1. Under **Register och enhet**, välj **SANFRAN-1**.
1. Välj **aktivera**. Du är utloggad och tagen till kassainloggningssidan.
1. Du kan nu logga in på molnbaserad kassaupplevelsen med operatörs-ID **000713** och lösenord **123**.

## <a name="set-up-your-e-commerce-sites"></a>Ställ in din webbplats för e-handel

Det finns tre tillgängliga demosplatser för e-handel: Fabrikam, Adventure Works och Adventure Works Business. Följ anvisningarna nedan och konfigurera varje demoplats.

1. Logga in på webbplatsskaparen med hjälp av den URL som du antecknade när du initierade näthandel under etableringen (se [initiera näthandel](provisioning-guide.md#initialize-e-commerce)).
1. Öppna siteinställningarna genom att välja siten (**Fabrikam**, **Adventure Works** eller **Adventure Works Business**).
1. Välj den domän som du angav när du initierade Commerce.
1. I administration väljer du den förkonfigurerade onlinebutikskanalen (**Fabrikam utökade onlinebutik**, **AW onlinebutik** eller **AW Business onlinebutik**) som motsvarar standardkanal.
1. För standardspråk väljer du **sv-SE**.
1. Konfigurera sökvägsfält. Denna kan lämnas tom för en enda webbplats, men måste konfigureras om du använder samma domännamn för flera webbplatser. Till exempel om domännamnet är `https://www.constoso.com`, kan du använda en tom sökväg för Fabrikam (`https://contoso.com`) och sedan "aw" för Adventure Works (`https://contoso.com/aw`) och "awbusiness" för Adventure Works Business webbplats (`https://contoso.com/awbusiness`).
1. Välj **OK**. Listan över sidor på webbplatsen visas.
1. Du kan även upprepa steg 2-7 och konfigurera de andra demowebbplatserna efter behov.

## <a name="enable-jobs"></a>Aktivera jobb

Gör så här om du vill aktivera jobb i Commerce.

1. Logga in på administrationsmiljön.
1. Gå till menyn till vänster **Retail och Commerce \> Förfrågningar och rapporter \> Batch-jobb**.

    De återstående stegen i den här proceduren måste slutföras för vart och ett av följande jobb:

    * Bearbeta butikorders e-postmeddelande
    * Produkttillgänglighet
    * P-0001
    * Synkronisera orderjobb

1. Använd snabbfiltret för att söka efter jobbet med hjälp av dess namn.
1. Utför följande steg om status för jobbet är **Kör**:

    1. Välj posten.
    1. I Åtgärdsfönstret på fliken **Batchjobb** välj **Ändra status**.
    1. Välj **Avbryt** och klicka sedan på **OK**.

1. Utför följande steg om status för jobbet är **Undandragen**:

    1. Välj posten.
    1. I Åtgärdsfönstret på fliken **Batchjobb** välj **Ändra status**.
    1. Välj **Väntar** och välj sedan **OK**.

Om du vill kan du också konfigurera upprepningsintervallet till en (1) minut för följande jobb:

* Bearbeta butikorders e-postmeddelandejobb
* P-0001 jobb
* Synkronisera orderjobb

### <a name="run-full-data-synchronization"></a>Kör fullständig datasynkronisering

Om du vill köra fullständig datasynkronisering i Commerce headquarters följ dessa steg.

1. Med hjälp av menyn till vänster, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> Commercesschemaläggare \> Kanaldatabas**.
1. Välj kanalen med namnet **scXXXXXXXXX**.
1. I åtgärdsfönstret, välj **Fullständig datasynkronisering**.
1. Ange **9999** som distributionsschema.
1. Välj **OK**.
1. Välj **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Testa kreditkortsinformation för att utföra testinköp

För att kunna utföra testtransaktioner på webbplatsen kan du använda den här kreditkortsinformationen för testet:

- **Kortnummer:** 4111-1111-1111-1111
- **Utgångsdatum:** 10/30
- **Kortverifieringsnummer (CVV) kod:** 737

> [!IMPORTANT]
> Du bör aldrig försöka använda äkta kreditkortsinformation på testwebbplatsen.

## <a name="next-steps"></a>Nästa steg

När etablerings- och konfigurationsstegen är slutförda kan du börja använda din sandbox-miljö. Använd Commerce URL:en för webbplatsskaparen för att gå till redigeringsupplevelsen. Använd URL:en för Commerce webbplats för att gå till näthandelssajt för butikskunden.

För att konfigurera valfria funktioner för Commerce sandbox-miljö, se [Konfigurera valfria funktioner för sandbox-miljö för Commerce](cpe-optional-features.md).

För att e-handelsanvändare ska kunna logga in på e-handelswebbplatsen krävs ytterligare konfiguration för att aktivera webbplatsautentisering via Azure Active Directory business-to-consumer (B2C). För instruktioner se [Ställa in en B2C-innehavare i Commerce](set-up-b2c-tenant.md).

## <a name="troubleshooting"></a>Felsökning

### <a name="site-builder-channel-list-is-empty-when-configuring-site"></a>Kanallistan för webbplatsbyggaren är tom när du konfigurerar webbplats

Om webbplatsbyggaren inte visar några onlinebutikskanaler ser du till att kanalerna har lagts till i Commerce Scale Unit enligt beskrivningen i avsnittet [Innan du startar](#before-you-start) ovan. Du kan också köra **initiera schemaläggare för handel** med värdet **Ta bort befintlig konfiguration** inställt på **Ja**.  När stegen är klara går du till sidan **Kanaldatabas** (**Butik och handel \> Administrationsinställning \> Handelsschemaläggare \> Kanaldatabas**) och kör jobbet **9999** på Commerce Scale Unit.

### <a name="color-swatches-are-not-rendering-on-the-category-page-but-are-rendering-on-the-product-details-page-pdp-page"></a>Färgrutor återges inte på kategorisidan, utan återges på sidan produktinformation (PDP)

Följ dessa steg för att se till att färg- och storleksrutor är inställda på att kunna förfinas.

1. I headquarters, gå till **Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.
1. Välj onlinebutikskanal i det vänstra fönstret och välj sedan **Ställ in attributmetadata**.
1. Ställ in **Visa attribut för kanal** till **Ja**, ställ in **Kan förfinas** till **Ja** och välj **Spara**. 
1. Gå tillbaka till sidan för onlinebutikskanal och välj **Publicera kanaluppdateringar**.
1. Gå till **Butik och handel \> Administrationsinställning \> Handelsschemaläggare \> Kanaldatabas** och kör jobbet **9999** på Commerce Scale Unit.

### <a name="business-features-dont-appear-to-be-turned-on-for-the-adventureworks-business-site"></a>Affärsfunktioner visas inte att vara aktiverad för affärswebbplatsen AdventureWorks

I headquarters ska du säkerställa att onlinebutikskanal är konfigurerad med **Kundtyp** inställd på **B2B**. Om **Kundtyp** inställd på **B2C** måste en ny kanal skapas eftersom den befintliga kanalen inte kan redigeras. 

Demodata levereras i Commerce version 10.0.26 och hade tidigare ett fel där kanalen **AW Business- onlinebutik** var felkonfigurerad. Lösningen är att skapa en ny kanal med samma inställningar och konfigurationer utom **Kundtyp**, som bör ställas in på **B2B**.

## <a name="additional-resources"></a>Ytterligare resurser

[Etablera en Dynamics 365 Commerce sandbox-miljö](provisioning-guide.md)

[Konfigurera valfria funktioner för en Dynamics 365 Commerce sandbox-miljö](cpe-optional-features.md)

[Konfigurera BOPIS i en Dynamics 365 Commerce sandbox-miljö](cpe-bopis.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portal](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce webbplatsen](https://aka.ms/Dynamics365CommerceWebsite)

[Ställa in en B2C-klientorganisation i Commerce](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
