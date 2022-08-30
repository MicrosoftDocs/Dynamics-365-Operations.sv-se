---
title: Chatta i Commerce med modulen Flerkanal för Customer Service
description: Den här artikeln beskriver Chatta i Commerce med modulen Flerkanal för Customer Service i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: e4a004b929138f0a04c19d6a94278cfad6e83303
ms.sourcegitcommit: 1dbff0b5fa1f4722a1720fac35cce94606fa4320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/24/2022
ms.locfileid: "9346404"
---
# <a name="commerce-chat-with-omnichannel-for-customer-service-module"></a>Chatta i Commerce med modulen Flerkanal för Customer Service

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Den här artikeln beskriver *Chatta i Commerce med modulen Flerkanal för Customer Service* i Microsoft Dynamics 365 Commerce.

I Commerce version 10.0.29 har en ny modul för Chatta i Commerce med Flerkanal för Customer Service lagts till i Commerce modulbiblioteket. Funktionen Chatta i Commerce ger e-handelskunder chattmöjligheter för Dynamics 365 Omnichannel for Customer Service, som inkluderar livesupport från handläggare för att hjälpa till att hantera kundfrågor, tillhandahålla kundservice och underlätta försäljning för Commerce-kunder.

Med hjälp av funktionen Chatta i Commerce kan återförsäljare uppnå följande mål:

- Öka det anpassade mötet med kunderna om du vill förbättra kundlojaliteten.
- Förbättra kundservicen genom integrationen av mänskliga handläggare och chattrobotar för självbetjäning.
- Hjälphandläggare får mer erfarenhet genom kundprofil, order och inköp i realtid som driver verksamhetens förbättringar och åtagande.
- Förbättra den generella kundnöjdheten för att öka försäljningen.

Följande funktioner är tillgängliga i funktionen Chatta i Commerce:

- Chatta i Commerce med Flerkanal för Customer Service
- Tillägget **Commerce kundtjänst Center** som en programflik i handläggarupplevelsen i Dynamics 365 Omnichannel for Customer Service

## <a name="prerequisites-for-omnichannel-for-customer-service"></a>Förutsättningar för Flerkanal för Customer Service

Som en förutsättning måste du konfigurera chatten i Flerkanal för Customer Service administration och skaffa dig några av parametrarna för att konfigurera upplevelsen chatta i Commerce. Instruktioner finns i [Konfigurera en chattkanal](/dynamics365/customer-service/set-up-chat-widget).

När du har konfigurerat en chatt i widgeten Flerkanal för Customer Service administration får du ett skript som liknar följande exempel.

`<script id="Microsoft_Omnichannel_LCWidget" src="https://oc-cdn-ocprod.azureedge.net/livechatwidget/scripts/LiveChatBootstrapper.js" data-app-id="xxxx-xxx-4be7-bcd5-1d118ecffe1f" data-org-id="5a0e73c0-xxxx-xxxxx-xxx- 76df135f375d" data-org-url="https://xxsxxxxssdb348f-crm.omnichannelengagementhub.com"></script>`

Kopiera det här skriptet eftersom du behöver värdena i det för att konfigurera chattmodulen.

### <a name="commerce-chat-with-omnichannel-for-customer-service-mandatory-fields"></a>Chatta i Commerce med modulen Flerkanal för Customer Service obligatoriska fält

Följande tabell visar skriptvärdena från widgeten administration för Flerkanal för Customer Service som krävs för att konfigurera Chatt i Commerce med Flerkanal för Customer Service.

| Widgetegenskap | Beskrivning |
| ------------- |--------------|
| Skriptkälla | Värdet på **src** i skriptet för chattwidget. |
| ID för dataapp | Värdet på **data-app-id** i skriptet för chattwidget. |
| Organisations-ID för data | Värdet på **data-org-id** i skriptet för chattwidget. |
| Organisations-ID för URL | Värdet på **data-org-url** i skriptet för chattwidget. |

## <a name="configure-the-commerce-chat-experience-for-your-e-commerce-site"></a>Konfigurera upplevelsen chatta i Commerce för din e-handelsplats

Ett rekommenderat sätt att implementera chattupplevelsen för din e-handelsplats är att lägga till Chatta i Commerce med modulen Flerkanal för Customer Service på den delade rubrikfragmentet som används på dina e-handelssidor.

Om du vill lägga till chattmodulen på din webbplats rubrikfragment i Commerce-webbplatsbyggaren följer du stegen nedan.

1. I webbplatsskaparen för din webbplats, gå till **Fragment**.
1. Välj **Ny**.
1. I dialogrutan **Välj ett fragment**, välj modulen **Chatta i Commerce med Flerkanal för Customer Service** ange ett namn för fragmentet och välj sedan **OK**.
1. I översikten väljer du platsen **Msdyn365 cs chat connector**.
1. I **Chattegenskaper** till höger följer du dessa steg:

    1. I fältet **Skriptkälla** anger du värdet **src** som du har fått från Flerkanal för Customer Service-skriptet.
    1. I fältet **Dataprogram-ID** anger du värdet **data-app-id** som du har fått från Flerkanal för Customer Service-skriptet.
    1. I fältet **Dataorganisations-ID** anger du värdet **data-org-id** som du har fått från Flerkanal för Customer Service-skriptet.
    1. I fältet **Dataorganisations-URL** anger du värdet **data-org-url** som du har fått från Flerkanal för Customer Service-skriptet.

    ![Skapa ett modulfragment för chatta i Commerce-webbplatsbyggaren.](media/Commerce-chat-creating-new-fragment.png)

1. Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.
1. Gå till **Fragment** och öppna rubrikfragmentet för webbplatsen.
1. På platsen **Standardbehållare** väljer du ellipsen (**...**) och sedan **Lägg till fragment**.
1. I dialogrutan **Välj moduler** väljer du det chattfragment som du skapade tidigare och väljer sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.

## <a name="add-commerce-headquarters-as-an-application-tab-for-omnichannel-for-customer-service"></a>Lägg till Commerce headquarters som en programflik för Flerkanal för Customer Service

Du kan lägga till en programflikför Commerce headquarters i Flerkanal för Customer Service. Livehandläggare kan sedan använda användargränssnittet för handläggarupplevelsen i Flerkanal för Customer Service för att enkelt komma åt Dynamics 365 Commerce kundtjänstmodul som innehåller kontextuell information för kunden tillsammans med deras försäljningsorderinformation. Dessutom kan kundtjänstpersonalen göra nya beställningar, initiera returer och verifiera orderstatusinformation.

### <a name="create-a-new-application-tab-that-loads-commerce-headquarters-in-an-iframe-module"></a>Skapa en ny programflik som läser in Commerce headquarters i en iFrame-modul 

För att skapa en ny programflik som läser in Commerce headquarters i en iFrame-modul följer du stegen nedan.

1. Öppna [Power Apps Maker Portal](https://make.powerapps.com).
1. I navigeringsfönstret till vänster, välj **Appar**.
1. Välj **administrationscenter för kundtjänst**.
1. Gå till **handläggarupplevelse**.
1. För **Mallar för programflikar**, välj **Hantera**.
1. Skapa en ny programflik av typen **Tredje parts webbplats**. För instruktioner, se [Hantera mallar för programflikar](/dynamics365/app-profile-manager/application-tab-templates?tabs=customerserviceadmincenter).
1. Under **Parametrar**, i fältet **Värde** för parameter **url** anger du följande URL, där `<YourOrganizationHeadquartersURL>` och `<LegalEntityname>` ersätts med tillämpliga värden. Flerkanal för Customer Service läser **{AccountNumber}** från chattkontexten. Lämna därför **{AccountNumber}** som det är.

    `https://<YourOrganizationHeadquartersURL>/?mi=MCRCustomerService&cmp=<LegalEntityName>&embedded=true&customerId={AccountNumber}`

1. Lämna fältet **Värde** i parametern **data** tom.

![Skapa en programflik i Dynamics 365 Flerkanal för Customer Service.](media/OC-CS-Admin-Application-Tab-Parameters.png)

## <a name="enable-a-new-application-tab-for-customer-agents-in-dynamics-365-omnichannel-for-customer-service"></a>Aktivera en ny programflik för kundhandläggare i Dynamics 365 Flerkanal för Customer Service

För att aktivera en ny programflik för kundhandläggare i Dynamics 365 Flerkanal för Customer Service, följ dessa steg.
    
1. Öppna [Power Apps Maker Portal](https://make.powerapps.com).
1. I navigeringsfönstret till vänster, välj **Appar**.
1. Välj **administrationscenter för kundtjänst**.
1. Gå till **kundsupport \>arbetsflöden**.
1. Öppna det arbetsflöde du har skapat för dina handläggare och välj sedan **Avancerade inställningar**, välj **Sessioner som standard**.
1. Under **Programflikar**, välj **Lägg till befintlig programflik** och lägg sedan till den nya programfliken som du skapade tidigare. Det här steget säkerställer att en programflik där Commerce headquarters i en iFrame-modul läses in när en agent får ett inkommande chattsamtal från din e-handelswebbplats.

## <a name="add-context-variables-in-dynamics-365-omnichannel-for-customer-service"></a>Lägga till sammanhangsvariabler i Dynamics 365 Flerkanal för Customer Service

För att lägga till sammanhangsvariabler i Dynamics 365 Flerkanal för Customer Service, följ dessa steg.

1. Öppna [Power Apps Maker Portal](https://make.powerapps.com).
1. I navigeringsfönstret till vänster, välj **Appar**.
1. Välj **administrationscenter för kundtjänst**.
1. Gå till **kundsupport \>arbetsflöden**.
1. Öppna det arbetsflöde du har skapat för dina handläggare och välj sedan **Avancerade inställningar**, gå till avsnittet **Sammanhangsvariabler**.
1. Välj **Redigera** och lägg sedan till **AccountNumber** som en sammanhangsvariabel av typen **text**. Den här variabeln gör det bättre att läsa in kundinformation med tillhörande kontonummer i Commerce headquarters.

> [!NOTE]
> Om du vill läsa e-postadresserna och namnen på inloggade användare från en e-handelskanal kan du lägga till **E-post** och **Namn** som sammanhangsvariabler av typen **text** utöver sammanhangsvariabeln **AccountNumber**.
