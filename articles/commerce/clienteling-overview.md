---
title: Översikt över klienteling
description: Det här avsnittet innehåller en översikt över nya klienteling funktioner som är tillgängliga i butiksappen.
author: bebeale
manager: AnnBe
ms.date: 01/29/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 206031f5ddbaedb2b581a452fe8979252647f0c4
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097265"
---
# <a name="clienteling-overview"></a>Översikt över kundhantering

[!include [banner](includes/banner.md)]


Många återförsäljare, särskilt de specialiserade återförsäljarna, vill att deras säljpartner ska bilda långsiktiga relationer med sina viktigaste kunder. Intresseföretag förväntas känna till om dessa kunders gillar och ogillar, inköps historik, produktinställningar och viktiga datum, t.ex. årsdagar och födelsedagar. Säljare behöver en plats där de kan samla in informationen och lätt hitta den när den behövs. Om denna information är tillgänglig i en enda vy, kan de enkelt rikta kunder som uppfyller specifika kriterier. De kan till exempel hitta alla kunder som föredrar att handla för handväskor, eller kunder som har en viktig händelse, t.ex. en födelsedag eller en årsdag.

## <a name="client-book"></a>Kundbok

I Microsoft Dynamics 365 Commerce kan återförsäljare använda kundboksfunktionen för att hjälpa till att lagra intresserelationer på lång sikt med viktiga kunder.

Kundboken innehåller kundkort som visar kontaktinformation för respektive kund tillsammans med tre ytterligare egenskaper som har definierats av återförsäljaren och konfigurerats i administrationen. Återförsäljare kan bestämma de tre viktigaste saker som säljfakturor ska känna till med kunderna. T.ex. återförsäljare av smycken kan inkludera viktiga datum, t.ex. årsdagar eller födelsedagar, eftersom dessa datum är speciella när andra kan köpa mer smycken. På samma sätt kan det vara en återförsäljare inom mode som vill inkludera kundens önskade shoppingintressen och varumärken.

Kundboken gör också att säljare filtrerar listan så att endast kunder som uppfyller specifika kriterier visas. En ny samling skor har till exempel anlänt till butiken och en ett intresse vill informera kunder som vill köpa skor. I detta fall kan säljaren filtrera kundboken för att hitta relevanta kunder och sedan vidta ytterligare åtgärder.

Om en kund inte längre betraktas som viktiga kunder av någon anledning och därför inte bör hanteras noga, kan säljaren ta bort dem från kundboken.

Vissa återförsäljare vill inte hantera kunder på säljarnivån. I stället vill de hantera en lista med viktiga kunder på butiksnivå. Dessa återförsäljare kan visa kunder från butikkundböcker. Med det här alternativet kan återförsäljare visa kunderna från kundböckerna i alla försäljare vars adressbok matchar adressboken för den aktuella butiken. Om en säljare arbetar i flera butiker av den juridiska personen visar kundboken kunderna från alla butikerna. Den här funktionen stöder ytterligare funktioner. Kunder kan till exempel tilldelas på nytt från ett och samma säljare till en säljare. Den här funktionen är användbar när affärspartner överförs eller lämnar företaget.

Varje säljare kan ha en kundbok per juridisk person och en säljare kan lägga till en eller flera kunder i sina kundböcker. I Commerce kan varje kund för närvarande endast läggas till i en kundbok. Microsoft planerar emellertid att lägga till funktioner som gör att en enskild kund kan läggas till i flera klientböcker.

> [!NOTE]
> Till skillnad från kundsökningen filtrerar kundboken inte kundposter baserat på butikens adressböcker.

## <a name="activities-and-notes"></a>Aktiviteter och anteckningar

Online-kanaler ger återförsäljare möjlighet att lära sig om kundinställningar utan att uttryckligen kräva att kunderna anger denna information. När kunder interagerar med säljare i butiken, delar de däremot uttryckligen information om sina önskemål. Tyvärr kan den här informationen gå förlorad efter försäljningen. Om den här informationen har registrerats kan den emellertid hjälpa återförsäljare att bättre förstå kunder och därmed hjälpa dem att ge bättre rekommendationer och en bättre övergripande kundupplevelse.

För att kunna fånga den viktiga information som kunderna delar kan säljarna inte bara använda kundboksattributen utan också använda funktionerna för aktiviteter och anteckningar. Återförsäljare kan konfigurera aktivitetstyper, till exempel information om butiksbesöket, e-postadress, telefonnummer och avtalade tider. Aktiviteter som säljare skapar kan visas i ett tidslinjeformat i POS. De kan också visas på fliken **aktiviteter** på sidan **alla kunder \> allmänt** i Administration.

Säljare kan också använda noteringar för att samla in allmän kundinformation som kan refereras före varje interaktion. Dessa anteckningar sparas i Administration och kan visas i kundprofilen eller på kunddetalj sidan i kundtjänst.

> [!NOTE]
> För närvarande kan alla anteckningar och aktiviteter visas av alla säljare som arbetar med den juridiska personen och som kan visa sidan med kundinformation. Anteckningar och aktiviteter begränsas inte till de som har lagt en kund i kundboken.

## <a name="integration-with-dynamics-365-customer-insights"></a>Integration med Dynamics 365 Customer Insights

Med hjälp av Dynamics 365 Customer Insights-programmet kan återförsäljare samla in data från de olika system som kunderna använder för att samverka med återförsäljarens varumärke. De kan sedan använda dessa data för att generera en enskild vy över kunden och härleda insikter. Med integrering av Customer Insights med Commerce kan återförsäljare välja ett eller flera mått som ska visas på kundkortet i kundboken. Återförsäljare kan till exempel använda data i Customer Insights för att beräkna "omsättningssannolikhet" för en kund och definiera nästa bästa åtgärd. Om dessa värden definieras som mått kan de visas på kundkortet och ge viktig information till säljare. Mer information om Customer Insights finns i [Dynamics 365 Customer Insights](https://docs.microsoft.com/dynamics365/ai/customer-insights/overview) dokumentation. Mer information om mått finns i [Mått](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).

## <a name="set-up-clienteling"></a>Ställ in klienteling

Om du vill aktivera klienteling-funktionen i din miljö följer du stegen nedan.

1. I arbetsytan **Funktionshantering** kan du filtrera funktionerna i modulen **Butik och handel**.

    ![Klienteling i listan över funktioner för modulen Commerce](./media/Enable_clienteling.png "Klienteling i listan över funktioner för modulen Butik och handel")

2. Aktivera funktionen **Klienteling** genom att välja **Aktivera nu**.
3. På sidan **handelsparametrar** väljer du fliken **Nummersekvens** och väljer raden **identifierare av klientbok**. Sedan i fältet **Nummersekvenskod** väljer du en nummersekvens. I systemet används den här nummerserien för att tilldela ett ID till klientböcker.
4. Välj **Spara**.
5. Skapa en ny attributgrupp som innehåller de attribut som du vill hämta för kunder som administreras i klientböcker. För instruktioner, se [Attribut och attributgrupper](https://docs.microsoft.com/dynamics365/retail/attribute-attributegroups-lifecycle).

    - Definiera de obligatoriska attributen **Kan förfinas**. Dessa attribut kan användas av säljare för att filtrera klientboken.
    - Ange visningsordning för dessa attribut. Den här visningsordningen avgör vilka attribut som ska visas på kundkortet i klientboken. Visningsordningen 1 betraktas som högre än visningsordningen 2. Därför visas attributet som har visningsordningen 1 framför attributet som har visningsordningen 2.

    > [!NOTE]
    > Du kan göra Customer Insights tillgängliga från samma sida. Däremot måste ett Azure program-ID och en hemlighet skapas, i syfte att autentiseras. (Mer information om kraven finns i avsnittet [aktivera integreringen av Customer Insights med Commerce](#turn-on-the-integration-of-customer-insights-with-commerce) senare i det här avsnittet.) Om Customer Insights aktiveras och du väljer en eller flera mått som ska visas på kundkortet visas dessa mått först. Därefter visas attributgrupper för klientbokgrupper baserat på visningsordningen. Om du till exempel väljer två mått från Customer Insights, visas dessa två mått och ett attribut för kundboken på kundkortet. (Attributet för kundboken som visas kommer att vara det attribut som har den högsta visningsordningen.)

6. På sidan **Handelsparametrar** på fliken **klienteling** i fältet **Attributgruppen kundbok** väljer du den attributgrupp som du just skapade.

    ![Vald attributgrupp för kundbok](./media/Client%20book%20attributes.png "Vald attributgrupp för kundbok")

7. Om du vill registrera aktiviteter som inträffar i POS definierar du aktivitetstyperna på sidan **aktivitetstyper** (**Butik och handel \> Kunder \> Aktivitetstyper**).

    > [!NOTE]
    > Aktivitetstyper hämtas av skalningsenhet för handel när den gör ett realtidssamtal för första gången. När aktiviteterna har hämtats cachelagras de under några timmar. Om du ändrar aktivitets typerna väntar du tills cachen inte längre är giltig. För miljöer utan produktionsmiljöer startar du om skalningsenhet för handel-tjänsten.

8. Lägg till två knappar i den lämpliga layouten för kassaskärmen, så att säljaren kan visa sin egen kundbok och butiks kundbok. (Butikkundböcker böcker omfattar kunder från alla kundböcker för alla som associerar en adressbok med butiken.) Motsvarande operationer kallas **Visa kunder i kundboken** och **Visa kunder från butikkundböcker**. Ytterligare tre operationer som rör kundböcker finns tillgängliga. Dessa operationer avgör vilka intresse företag som kan lägga till, ta bort och tilldela om kunder från kundboken. De namnges **Lägg till kund i kundboken**, **Ta bort kunder från kundboken** och **Tilldela om kunder till en klientbok**.
9. Kör följande jobb för distributionsschema: 1040, 1150, 1110 och 1090.

När du har slutfört den här proceduren kan säljarna öppna kunddetaljsidan i POS och lägga till kunder i sin kundbok, visa och fånga in aktiviteter och noteringar för kunder och mål kunder genom att använda attribut för kund och klientbok för att filtrera kundboken. Illustrationen nedan visar ett exempel på en kundbok.

![Exempel på en kundbok](./media/client_book.png "Exempel på en kundbok")

## <a name="turn-on-the-integration-of-customer-insights-with-commerce"></a>Aktivera integreringen av Customer Insights med Commerce

Om du vill aktivera integrationen av Customer Insights med Commerce måste du se till att du har en aktiv instans av Customer Insights i innehavaren där Commerce har etablerats. Du måste också ha ett Azure Active Directory (Azure AD)-användarkonto med en Azure-prenumeration.

Följ dessa steg för att ställa in integrationen.

1. Registrera ett nytt program i Azure-portalen och notera programnamn, program-ID och hemlighet. Denna information används för verifiering av tjänst-till-tjänst mellan Commerce och Customer Insights. Notera hemligheten på ett säkert sätt då den krävs för att spara informationen i nyckelvalvet. I följande exempel ska du använda CI_Access_name, CI_Access_AppID, CI_Access_Secret för programnamn, program-ID respektive hemlighet. Mer information [Snabbstart: registrera ett program med Microsoft identitetsplattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

    > [!IMPORTANT]
    > Vidta åtgärder så att du kommer ihåg att ändra hemligheten innan den upphör att gälla. I annat fall stoppas integrationen oväntat.

2. Gå till din Customer Insights-instans och sök efter namnet på det program som har skapats ovan (i det här exemplet "CI_Access_name").
3. Skapa ett Azure KEy Vault och notera namn och webbadress (URL; i detta exempel "KeyVaultName", "KeyVaultURL"). Instruktioner finns i [snabbstart: ställ in och hämta en hemlighet från Azure Key Vault med hjälp av Azure-portalen](https://docs.microsoft.com/azure/key-vault/quick-create-portal).
4. Spara hemligheten (i detta exempel "CI_Access_Secret") i valvet. När denna hemlighet lagras i valvet får den ett namn. Notera hemlighetens namn (i detta exempel "SecretName").
5. Om du vill komma åt hemligheten från Azure Key Vault måste du skapa ett annat program med ett program-ID och en hemlighet (i detta exempel "KeyVault_Access_AppID" och "KeyVault_Access_Secret"). Notera hemligheten säkert eftersom den inte kommer att visas igen.
6. Du måste sedan ge behörighet till programmet för åtkomst till Key Vault från Commerce med hjälp av API:er. I Azure portal går du till programsidan. I avsnittet **Hantera** väljer du **API-behörigheter**. Lägg till behörigheten till för åtkomst till **Azure Key Vault**. Välj **Åtkomstpolicy** för denna behörighet. Välj mallen som **Hemlighetshantering** och sedan alternativen **Hämta**, **Lista**, **Avkryptera** och **Kryptera**. 
5. In Commerce-administrationen går du till **Systemadministration \> Inställningar \> Parametrar för Key Vault** och anger den information som krävs för nyckelvalvet. I fältet **Key Vault-klient** anger du det program-ID som du använde i steg 4, så att Commerce kan komma åt hemligheterna i Key Vault.
6. Om du vill lägga till det program som du skapade i steg 1 i listan över säkra program (kallas ibland för "säker lista"), går du till Customer Insights och väljer **Visa** åtkomst till programmet. För anvisningar, se [Behörigheter](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-permissions).
7. På sidan **Systemadministration > Inställningar > Parametrar för nyckelvalv** i Commerce HQ uppdaterar du fälten enligt nedan: 

- **Url för nyckelvalv** : "KeyVaultURL" (från steg 3 ovan).
- **Nyckelvalvsklient**: "KeyVault_Access_AppID" (från steg 5 ovan).
- **Hemlig nyckel för nyckelvalv**: "KeyVault_Access_Secret" (från steg 5 ovan).
- Under avsnittet **Hemligheter**:
    - **Namn**: Valfritt namn, t.ex. "CISecret".
    - **Beskrivning**: Alla värden.
    - **Hemlighet**: **valv**://<Name of key vault>/<name of secret>> I detta exempel blir detta "vault://KeyVaultName/SecretName".

När du har uppdaterat fälten väljer du **Validera** för att säkerställa att hemligheten kan nås från programmet Commerce.

8. På sidan **Commerce-parametrar** i Commerce, på fliken **Klienter** på snabbfliken **Dynamics 365 Customer Insights**, anger du **Program-ID** som "CI_Access_AppID" (från steg 1 ovan). För **Hemligt namn** väljer du namnet på den hemlighet som angavs i steg 7 ovan ("CISecret"). Ange alternativet **Aktivera Customer Insights** till **Ja**. Om inställningen misslyckas visas ett felmeddelande, och detta alternativ anges som **Nej**. 

Du kan ha flera miljöer i Customer Insights, t.ex. test- och produktionsmiljöer. I fältet **miljöinstans-ID** anger du lämplig miljö. I fältet **alternativt kund-ID** anger du egenskapen i Customer Insights som har mappats till kundkontonumret. (I Commerce är kundens kontonummer kundens ID) Återstående tre egenskaper är de mått som anges på kundkortet i klientboken. Du kan välja upp till tre mått som ska visas på kundkortet. Du måste dock inte välja några mått. Som tidigare har nämns visar systemet först dessa värden, för att sedan visa värdena för attributgruppen i klientboken.
