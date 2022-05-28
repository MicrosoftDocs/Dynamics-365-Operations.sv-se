---
title: Konfigurera en Dynamics 365 Commerce utvärderingsmiljö
description: Detta ämne förklarar hur du konfigurerar bedömningsmiljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.
author: psimolin
ms.date: 05/12/2022
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
ms.openlocfilehash: d9738700ca495d54c91ad91aa9c5a3d32c95a5a5
ms.sourcegitcommit: 4a973ac0e7af0176270a8070a96a52293567dfbf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8747647"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a>Konfigurera en Dynamics 365 Commerce utvärderingsmiljö

[!include [banner](includes/banner.md)]

Detta ämne förklarar hur du konfigurerar bedömningsmiljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.

Slutför procedurerna i det här avsnittet först när bedömningsmiljö för Commerce har etablerats. Information om hur du konfigurerar etablerar bedömningsmiljö för Commerce, se [Etablera en bedömningsmiljö för Commerce](provisioning-guide.md).

När din bedömningsmiljö för Commerce har etablerats måste ytterligare konfigurationssteg för efter etableringen slutföras innan du kan börja utvärdera miljön. Om du vill utföra dessa steg måste du använda Microsoft Dynamics Lifecycle Services (LCS) och Dynamics 365 Commerce.

## <a name="before-you-start"></a>Innan du börjar

1. Logga in på [LCS-portal](https://lcs.dynamics.com).
1. Gå till ditt projekt.
1. På huvudmenyn väljer du miljön **Molnstyrda miljöer**.
1. Välj din miljö i listan.
1. Välj i miljöinformation till höger **Logga in i miljön**. Du kommer att skickas till Commerce-administration.
1. Kontrollera att **USRT** juridisk person har valts i övre högra hörnet.
1. Gå till **Handelsparametrar \> Konfigurationsparametrar** och se till att det finns en post för **ProductSearch.UseAzureSearch** och att värdet är **true**. Om den här posten saknas kan du lägga till den, ange värdet **true** och välja **Kanaldatabas \> Fullständig datasynkronisering** för den Commerce Scale Unit som är associerad med din näthandelsplats.
1. Gå till **Butik och handel \> Administrationsinställning \> Schemaläggare för handel \> Initiera schemaläggare för handel**. På den utfällbara menyn **Initiera schemaläggare för handel** se till att alternativet **Ta bort befintligt konfiguration** anges till **Ja** och välj **OK**.
1. För att lägga till kanaler i Commerce Scale Unit, gå till **Butik och handel \> Administrationsinställning \> Handelsschemaläggare \>Kanaldatabas** och välj Commerce Scale Unit i vänstra fönstret. På snabbfliken **Butikskanal**, lägg till kanalerna **AW-onlinebutik**, **AW Business-onlinebutik** och **Fabrikam utökade online-butik**. Alternativt kan du också lägga till detaljhandelsbutiker om du ska använda kassa (till exempel **Seattle**, **San Francisco** och **San Jose**).

Under åtgärderna efter etablering i Commerce-administration, se till att den juridiska personen **USRT** alltid är vald.

## <a name="configure-the-point-of-sale"></a>Konfigurera POS

### <a name="associate-a-worker-with-your-identity"></a>Associera medarbetare med din identitet

Om du vill associera en anställd med din identitet, följ dessa steg i Commerce-administration.

1. Använd menyn till vänster för att gå till **moduler \> Retail och Commerce \> anställda \> medarbetare**.
1. Hitta och markera följande post: **000713 – Andrew Collette** i listan.
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

## <a name="set-up-your-site-in-commerce"></a>Ställ in din webbplats i Commerce

Följ dessa steg om du vill börja konfigurera din bedömningswebbplats i Commerce.

1. Logga in på webbplatsskaparen med hjälp av den URL som du antecknade när du initierade näthandel under etableringen (se [initiera näthandel](provisioning-guide.md#initialize-e-commerce)).
1. Klicka på på webbplatsen **Fabrikam** för att öppna dialogrutan webbplatsinställningar.
1. Välj den domän som du angav när du initierade näthandel.
1. Som standardkanal väljer du **Fabrikam utökade online-butik**. (Se till att välja den **utökade** onlinebutiken)
1. För standardspråk väljer du **sv-SE**.
1. Lämna värdet i fältet **sökväg** som det är.
1. Välj **OK**. Listan över sidor på webbplatsen visas.
1. Upprepa steg 2–7 för webbplatsen **AdventureWorks** (som mappas till kanalen **AW-onlinebutik**) och webbplatsen **AdventureWorks Business** (som mappar till kanalen **AW Business-onlinebutik**). Om fältet **Sökväg** för Fabrikam-webbplatsen är tomt måste du lägga till sökvägar för de två AdventureWorks-webbplatserna (till exempel "aw" och "awbusiness").

## <a name="enable-jobs"></a>Aktivera jobb

Gör så här om du vill aktivera jobb i Commerce.

1. Logga in på miljön (HQ).
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

Om du vill kan du också ställa in upprepningsintervallet till en (1) minut för följande jobb:

* Bearbeta butikorders e-postmeddelandejobb
* P-0001 jobb
* Synkronisera orderjobb

### <a name="run-full-data-synchronization"></a>Kör fullständig datasynkronisering

Om du vill köra fullständig datasynkronisering i Commerce-administration följ dessa steg.

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

När etablerings- och konfigurationsstegen är slutförda kan du börja använda din bedömningsmiljö. Använd Commerce URL:en för webbplatsskaparen för att gå till redigeringsupplevelsen. Använd URL:en för Commerce webbplats för att gå till näthandelssajt för butikskunden.

För att konfigurera valfria funktioner för Commerce bedömningsmiljö efter att du har konfigurerat den finns i [Konfigurera valfria funktioner för bedömningsmiljö för Commerce](cpe-optional-features.md).

> [!NOTE]
> Med utvärderingsmiljöer för Commerce följer en förinläst Azure Active Directory (Azure AD) B2C(business-to-consumer)-klientorganisation för demonstrationssyften. Konfigurering av en egen Azure AD B2C-klientorganisation krävs inte för utvärderingsmiljöer. Om du konfigurerar utvärderingsmiljön för att använda din egen Azure AD B2C-klientorganisation ska du emellertid se till att lägga till ``https://login.commerce.dynamics.com/_msdyn365/authresp`` som en svars-URL i Azure AD B2C-programmet via Azure Portal.

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

[Dynamics 365 Commerce bedömningsmiljö – översikt](cpe-overview.md)

[Etablera en Dynamics 365 Commerce bedömningsmiljön](provisioning-guide.md)

[Konfigurera valfria funktioner för en Dynamics 365 Commerce bedömningsmiljö](cpe-optional-features.md)

[Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö](cpe-bopis.md)

[Dynamics 365 Commerce bedömningsmiljö – vanliga frågor](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portal](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce webbplatsen](https://aka.ms/Dynamics365CommerceWebsite)

[Ställa in en B2C-klientorganisation i Commerce](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
