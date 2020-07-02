---
title: Översikt över klienteling
description: Det här avsnittet innehåller en översikt över nya klienteling funktioner som är tillgängliga i butiksappen.
author: bebeale
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: d76668fa16a7634e7fbd953afaa6c89eed5457a2
ms.sourcegitcommit: 21943fa91c35f063a5bd064290bf2c005394df52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2020
ms.locfileid: "3456517"
---
# <a name="clienteling-overview"></a>Översikt över kundhantering

[!include [banner](includes/banner.md)]


Många återförsäljare, särskilt de specialiserade återförsäljarna, vill att deras säljpartner ska bilda långsiktiga relationer med sina viktigaste kunder. Intresseföretag förväntas känna till om dessa kunders gillar och ogillar, inköps historik, produktinställningar och viktiga datum, t.ex. årsdagar och födelsedagar. Säljare behöver en plats där de kan samla in informationen och lätt hitta den när den behövs. Om denna information är tillgänglig i en enda vy, kan de enkelt rikta kunder som uppfyller specifika kriterier. De kan till exempel hitta alla kunder som föredrar att handla för handväskor, eller kunder som har en viktig händelse, t.ex. en födelsedag eller en årsdag.

## <a name="client-book"></a>Kundbok

I Microsoft Dynamics 365 Commerce kan återförsäljare använda kundboksfunktionen för att hjälpa till att lagra intresserelationer på lång sikt med viktiga kunder.

kundboken innehåller kundkort som visar kontakt information för varje kund, tillsammans med tre ytterligare egenskaper som har definierats av åter försäljaren och konfigurerats i administration. Återförsäljare kan bestämma de tre viktigaste saker som säljfakturor ska känna till med kunderna. T.ex. återförsäljare av smycken kan inkludera viktiga datum, t.ex. årsdagar eller födelsedagar, eftersom dessa datum är speciella när andra kan köpa mer smycken. På samma sätt kan det vara en återförsäljare inom mode som vill inkludera kundens önskade shoppingintressen och varumärken.

Kundboken gör också att säljare filtrerar listan så att endast kunder som uppfyller specifika kriterier visas. En ny samling skor har till exempel anlänt till butiken och en ett intresse vill informera kunder som vill köpa skor. I detta fall kan säljaren filtrera kundboken för att hitta relevanta kunder och sedan vidta ytterligare åtgärder.

Om en kund inte längre betraktas som viktiga kunder av någon anledning och därför inte bör hanteras noga, kan säljaren ta bort dem från kundboken.

Vissa återförsäljare vill inte hantera kunder på säljarnivån. I stället vill de hantera en lista med viktiga kunder på butiksnivå. Dessa återförsäljare kan visa kunder från butikkundböcker. Med det här alternativet kan återförsäljare visa kunderna från kundböckerna i alla försäljare vars adressbok matchar adressboken för den aktuella butiken. Om en säljare arbetar i flera butiker av den juridiska personen visar kundboken kunderna från alla butikerna. Den här funktionen stöder ytterligare funktioner. Kunder kan till exempel tilldelas på nytt från ett och samma säljare till en säljare. Den här funktionen är användbar när affärspartner överförs eller lämnar företaget.

Varje säljare kan ha en kundbok per juridisk person och en säljare kan lägga till en eller flera kunder i sina kundböcker. I Handel kan varje kund för närvarande endast läggas till i en kundbok. Microsoft planerar emellertid att lägga till funktioner som gör att en enskild kund kan läggas till i flera klientböcker.

> [!NOTE]
> Till skillnad från kundsökningen filtrerar kundboken inte kundposter baserat på butikens adressböcker.

## <a name="activities-and-notes"></a>Aktiviteter och anteckningar

Online-kanaler ger återförsäljare möjlighet att lära sig om kundinställningar utan att uttryckligen kräva att kunderna anger denna information. När kunder interagerar med säljare i butiken, delar de däremot uttryckligen information om sina önskemål. Tyvärr kan den här informationen gå förlorad efter försäljningen. Om den här informationen har registrerats kan den emellertid hjälpa återförsäljare att bättre förstå kunder och därmed hjälpa dem att ge bättre rekommendationer och en bättre övergripande kundupplevelse.

För att kunna fånga den viktiga information som kunderna delar kan säljarna inte bara använda kundboksattributen utan också använda funktionerna för aktiviteter och anteckningar. Återförsäljare kan konfigurera aktivitetstyper, till exempel information om butiksbesöket, e-postadress, telefonnummer och avtalade tider. Aktiviteter som säljare skapar kan visas i ett tidslinjeformat i kassan (POS). De kan också visas på fliken **aktiviteter** på sidan **alla kunder \> allmänt** i Administration.

Säljare kan också använda noteringar för att samla in allmän kundinformation som kan refereras före varje interaktion. Dessa anteckningar sparas i Administration och kan visas i kundprofilen eller på kunddetalj sidan i kundtjänst.

> [!NOTE]
> För närvarande kan alla anteckningar och aktiviteter visas av alla säljare som arbetar med den juridiska personen och som kan visa sidan med kundinformation. Anteckningar och aktiviteter begränsas inte till de som har lagt en kund i kundboken.

## <a name="integration-with-dynamics-365-customer-insights"></a>Integration med Dynamics 365 Customer Insights

Med hjälp av Dynamics 365 Customer Insights-programmet kan återförsäljare samla in data från de olika system som kunderna använder för att samverka med återförsäljarens varumärke. De kan sedan använda dessa data för att generera en enskild vy över kunden och härleda insikter. Med integrering av Customer Insights med Handel kan återförsäljare välja ett eller flera mått som ska visas på kundkortet i kundboken. Återförsäljare kan till exempel använda data i Customer Insights för att beräkna "omsättningssannolikhet" för en kund och definiera nästa bästa åtgärd. Om dessa värden definieras som mått kan de visas på kundkortet och ge viktig information till säljare. Mer information om Customer Insights finns i [Dynamics 365 Customer Insights](https://docs.microsoft.com/dynamics365/ai/customer-insights/overview) dokumentation. Mer information om mått finns i [Mått](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).

## <a name="set-up-clienteling"></a>Ställ in klienteling

Om du vill aktivera klienteling-funktionen i din miljö följer du stegen nedan.

1. I arbetsytan **Funktionshantering** kan du filtrera funktionerna i modulen **Butik och handel**.

    ![Klienteling i listan över funktioner för modulen Handel](./media/Enable_clienteling.png "Klienteling i listan över funktioner för modulen Butik och handel")

2. Aktivera funktionen **Klienteling** genom att välja **Aktivera nu**.
3. På sidan **handelsparametrar** väljer du fliken **Nummersekvens** och väljer raden **identifierare av klientbok**. Sedan i fältet **Nummersekvenskod** väljer du en nummersekvens. I systemet används den här nummerserien för att tilldela ett ID till klientböcker.
4. Välj **Spara**.
5. Skapa en ny attributgrupp som innehåller de attribut som du vill hämta för kunder som administreras i klientböcker. För instruktioner, se [Attribut och attributgrupper](https://docs.microsoft.com/dynamics365/retail/attribute-attributegroups-lifecycle).

    - Definiera de obligatoriska attributen **Kan förfinas**. Dessa attribut kan användas av säljare för att filtrera klientboken.
    - Ange visningsordning för dessa attribut. Den här visningsordningen avgör vilka attribut som ska visas på kundkortet i klientboken. Visningsordningen 1 betraktas som högre än visningsordningen 2. Därför visas attributet som har visningsordningen 1 framför attributet som har visningsordningen 2.

    > [!NOTE]
    > Du kan göra Customer Insights tillgängliga från samma sida. Däremot måste ett Azure program-ID och en hemlighet skapas, i syfte att autentiseras. (Mer information om kraven finns i avsnittet [aktivera integreringen av Customer Insights med Handel](#turn-on-the-integration-of-customer-insights-with-commerce) senare i det här avsnittet.) Om Customer Insights aktiveras och du väljer en eller flera mått som ska visas på kundkortet visas dessa mått först. Därefter visas attributgrupper för klientbokgrupper baserat på visningsordningen. Om du till exempel väljer två mått från Customer Insights, visas dessa två mått och ett attribut för kundboken på kundkortet. (Attributet för kundboken som visas kommer att vara det attribut som har den högsta visningsordningen.)

6. På sidan **Handelsparametrar** på fliken **klienteling** i fältet **Attributgruppen kundbok** väljer du den attributgrupp som du just skapade.

    ![Vald attributgrupp för kundbok](./media/Client%20book%20attributes.png "Vald attributgrupp för kundbok")

7. Om du vill registrera aktiviteter som inträffar i kassan definierar du aktivitetstyperna på sidan **aktivitetstyper** (**Butik och handel \> Kunder \> Aktivitetstyper**).

    > [!NOTE]
    > Aktivitetstyper hämtas av skalningsenhet för handel när den gör ett realtidssamtal för första gången. När aktiviteterna har hämtats cachelagras de under några timmar. Om du ändrar aktivitets typerna väntar du tills cachen inte längre är giltig. För miljöer utan produktionsmiljöer startar du om skalningsenhet för handel-tjänsten.

8. Lägg till två knappar i den lämpliga layouten för kassaskärmen, så att säljaren kan visa sin egen kundbok och butiks kundbok. (Butikkundböcker böcker omfattar kunder från alla kundböcker för alla som associerar en adressbok med butiken.) Motsvarande operationer kallas **Visa kunder i kundboken** och **Visa kunder från butikkundböcker**. Ytterligare tre operationer som rör kundböcker finns tillgängliga. Dessa operationer avgör vilka intresse företag som kan lägga till, ta bort och tilldela om kunder från kundboken. De namnges **Lägg till kund i kundboken**, **Ta bort kunder från kundboken** och **Tilldela om kunder till en klientbok**.
9. Kör följande jobb för distributionsschema: 1040, 1150, 1110 och 1090.

När du har slutfört den här proceduren kan säljarna öppna kunddetaljsidan i kassan och lägga till kunder i sin kundbok, visa och fånga in aktiviteter och noteringar för kunder och mål kunder genom att använda attribut för kund och klientbok för att filtrera kundboken. Illustrationen nedan visar ett exempel på en kundbok.

![Exempel på en kundbok](./media/client_book.png "Exempel på en kundbok")

## <a name="turn-on-the-integration-of-customer-insights-with-commerce"></a>Aktivera integreringen av Customer Insights med Handel

Om du vill aktivera integrationen av Customer Insights med Handel måste du se till att du har en aktiv instans av Customer Insights i innehavaren där Handel har etablerats. Du måste också ha ett Azure Active Directory (Azure AD)-användarkonto med en Azure-prenumeration.

Följ dessa steg för att ställa in integrationen.

1. Registrera ett program i Azure-portalen. Det här programmet kommer att användas för autentisering med Customer Insights. Instruktioner finns i [snabbstart: registrera ett program med Microsoft identitetsplattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).
2. Generera en hemlighet för programmet. Anteckna hemligheten och förvara den någonstans där, eftersom du kommer att behöva den senare. Välj också förfallotid för hemligheten.

    > [!IMPORTANT]
    > Vidta åtgärder så att du kommer ihåg att ändra hemligheten innan den upphör att gälla. I annat fall stoppas integrationen oväntat.

3. Skapa ett Azure Key Vault och spara programhemligheten. Instruktioner finns i [snabbstart: ställ in och hämta en hemlighet från Azure Key Vault med hjälp av Azure-portalen](https://docs.microsoft.com/azure/key-vault/quick-create-portal).
4. Aktivera åtkomst till Azure Key Vault från Handel. För att slutföra det här steget måste du ha ett program-ID och en hemlighet. Programmet kan vara samma program som du skapade i steg 1, eller så kan det vara ett nytt program. (Med andra ord kan du använda det program som du skapade i steg 1 för både åtkomst till Key Vault valv och Customer Insights service, eller så kan du skapa ett unikt program för varje typ av åtkomst.) Instruktioner finns i [lagra autentiseringsuppgifter för Service Principals i Azure Stack Key Vault](https://docs.microsoft.com/azure-stack/user/azure-stack-key-vault-store-credentials?view=azs-1908#create-a-service-principal).
5. In Administration, gå till **Systemadministration \> Inställningar \> Parametrar för Key Vault** och ange den information som krävs för Key Vault. I fältet **Key Vault-klient** anger du det program-ID som du använde i steg 4, så att Handel kan komma åt hemligheterna i Key Vault.
6. Om du vill lägga till det program som du skapade i steg 1 i listan över säkra program (kallas ibland för säker lista), går du till Customer Insights och ger åtkomst **Visa** till programmet. För anvisningar, se [Behörigheter](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-permissions).
7. I Handel, på sidan **Handel-parametrar** på fliken **klienteling** på snabbfliken **Dynamics 365 Customer Insights** följ dessa steg:

    1. I fältet **program-ID** ange det program-ID du använde i steg 1.
    2. I fältet **Hemligt namn** anger du namnet på den Key Vault-hemlighet som du valde i steg 5.
    3. Ange alternativet **Aktivera Customer Insights** till **Ja**. Om inställningen misslyckas får du ett felmeddelande och detta alternativ kommer att anges till **nej**.
    4. Du kan ha flera miljöer i Customer Insights, t.ex. test- och produktionsmiljöer. I fältet **miljöinstans-ID** anger du lämplig miljö.
    5. I fältet **alternativt kund-ID** anger du egenskapen i Customer Insights som har mappats till kundkontonumret. (I Handel är kundkontonumret kundens ID.)
    6. De återstående tre egenskaperna är de mått som kommer att visas på kundkortet i kundboken. Du kan välja upp till tre mått som ska visas på kundkortet. (Du behöver dock inte markera några mått.) Som tidigare nämnts visar systemet dessa värden först och sedan visas värdena för attributgruppen för kundboksgruppen.
