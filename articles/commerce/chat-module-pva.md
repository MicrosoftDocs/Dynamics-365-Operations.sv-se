---
title: Commerce-chatt med Power Virtual Agents-modul
description: I den här artikeln beskrivs Commerce-chatten med Power Virtual Agents modul som integrerar Microsoft Power Virtual Agents med Dynamics 365 Commerce-webbplatser.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-07
ms.openlocfilehash: 838990cb638479c9c90ba0e38794ecedd55e95b3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691108"
---
# <a name="commerce-chat-with-power-virtual-agents-module"></a>Commerce-chatt med Power Virtual Agents-modul

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs Commerce-chatten med Power Virtual Agents modul som integrerar Microsoft Power Virtual Agents med Dynamics 365 Commerce-webbplatser.

Commerce-chatt med Power Virtual Agents-funktionen gör det möjligt för Dynamics 365-kunder att använda Power Virtual Agents chattfunktionen och hantera sina frågor. Från och med Dynamics 365 Commerce 10.0.30 versionen, den här funktionen kan integreras i e-handelswebbplatser genom att använda chatt i Commerce med Power Virtual Agents modulen som ingår i Commerce modulbiblioteket.

Chatt i Commerce med funktionen Power Virtual Agents hjälper företag att uppnå följande mål:

- Öka personligt engagemang med kunderna och förbättra kvarhållande.
- Öka kundservicen genom integrationen av chattrobotar för självbetjäning.
- Öka den generella kundnöjdheten och öka försäljningen.

> [!NOTE]
> Information om skillnaderna mellan Dynamics 365 Omnichannel for Customer Service och Power Virtual Agents-appar finns i [Översikt över modulen Chatt i Commerce](/commerce-chat-modules-overview.md).

## <a name="prerequisites-for-using-power-virtual-agents"></a><a id="prereq"></a>Förutsättningar för att använda Power Virtual Agents

Om du vill använda funktionen chatt i Commerce med Power Virtual Agents måste du först skapa en Power Virtual Agents chattfunktion för din e-handelswebbplats. Instruktioner finns i [Skapa en robot för virtuell handläggare](/power-virtual-agents/authoring-first-bot).

När du har konfigurerat chattfunktionen måste du kopiera värdet för parametrarna för chattrobot **Robot-ID** och **Innehavar-ID** för att konfigurera Commerce chattupplevelsen. Information om hur du kopierar dessa värden finns i [Hämta dina Power Virtual Agents robotparametrar](/power-virtual-agents/publication-connect-bot-to-custom-application#retrieve-your-power-virtual-agents-bot-parameters).

## <a name="configure-your-e-commerce-site"></a>Konfigurera din näthandelssajt 

Ett rekommenderat sätt att implementera chattupplevelsen för din e-handelsplats är att lägga till Chatta i Commerce med modulen Power Virtual Agents på den delade rubrikfragmentet som används på dina e-handelssidor.

Om du vill lägga till chattmodulen på din webbplats rubrikfragment i Commerce-webbplatsbyggaren följer du stegen nedan.

1. I Commerce webbplatsskaparen för din webbplats, gå till **Fragment**.
1. Välj **Ny**.
1. I dialogrutan **Välj ett fragment**, välj modulen **Chatta i Commerce med Power Virtual Agents** ange ett namn för fragmentet och välj sedan **OK**.
1. I översikten väljer du platsen **Msdyn365 pva chat connector**.
1. I fönstret egenskaper till höger följer du dessa steg:

    1. Under **Robotparametrar**, i fältet **Bot Framework webbchatt chatt CDN URL** lämnar du standardvärdet (till exempel `https://cdn.botframework.com/botframework-webchat/latest/webchat.js`).
    1. I fältet **Bot Framework Direct Line autentiserings-URL** lämnar du standardvärdet (till exempel `https://powerva.microsoft.com/api/botmanagement/v1/directline/directlinetoken`).
    1. I fältet **Robot-ID** anger du värdet Power Virtual Agents **Robot-ID** som du kopierade i avsnittet [Förutsättningar för användning Power Virtual Agents](#prereq).
    1. I fältet **Innehavar-ID** ange värdet **Innehavar-ID** som du kopierade.

1. Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.
1. Gå till **Fragment** och öppna rubrikfragmentet för webbplatsen.
1. På platsen **Standardbehållare** väljer du ellipsen (**...**) och sedan **Lägg till fragment**.
1. I dialogrutan **Välj moduler** väljer du det chattfragment som du skapade tidigare och väljer sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.

## <a name="proactive-chat-parameters"></a>Proaktiva chattparametrar

För en komplett lista över parametrar för proaktiv chattkonfiguration, se [Commerce chattmodulens proaktiva chattparametrar](chat-proactive-chat-parameters.md).

> [!NOTE]
> Aktuella Power Virtual Agents stöder inte Azure Active Directory B2C (Azure AD B2C) autentisering. Det stöder bara anonyma Retail Cloud Scale Unit (RCSU) anrop för att få produkttillgänglighet eller samverka med andra anonyma API:er. Samtal till autentiserade API:er via Power Virtual Agents en chattfil kräver en explicit inloggning för kunder.

## <a name="additional-resources"></a>Ytterligare resurser

[Funktioner för Commerce-chatt](commerce-chat-overview.md)

[Chatta i Commerce med modulen Flerkanal för Customer Service](commerce-chat-module.md)

[Förebyggande chattparametrar för Commerce-chattmodulen](chat-proactive-chat-parameters.md)
