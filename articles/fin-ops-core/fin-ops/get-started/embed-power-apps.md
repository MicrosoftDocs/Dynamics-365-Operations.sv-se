---
title: Bädda in Power Apps
description: Det här avsnittet beskriver hur du bäddar in Power Apps till klienten för att utöka produktens funktionalitet.
author: jasongre
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 9585d5a399ebf45b0ad7640f3c4e48d8afc46cd8
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017738"
---
# <a name="embed-microsoft-power-apps"></a>Bädda in Microsoft Power Apps

[!include [banner](../includes/banner.md)]

I plattformsuppdatering stöder Finance and Operations integrering med Microsoft Power Apps en tjänst för utvecklare och icke-tekniska användare för att skapa anpassade affärsappar för mobila enheter, surfplattor och webb utan att skriva kod. Power Apps utvecklats av dig, ditt företag eller det bredare ekosystemet och kan sedan bäddas in i Finance and Operations-appar utöka produktens funktioner. Exempelvis kan du skapa ett program från Power Apps som kompletterar en Finance and Operations-app med information som hämtas från ett annat system.

Om du vill veta mer om inbäddning av Power Apps kan du titta på den korta videon [Så här bäddar du in Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-app-from-power-apps-to-a-page"></a>Lägger till en inbäddad app från Power Apps på en sida

### <a name="overview"></a>Översikt

När du infogar en app från Power Apps till klienten måste du först hitta eller skapa en app med önskade bilder och/eller funktioner. Vi kommer inte att beskriva den detaljerade processen för att bygga en app här. Ämnet [Introduktion till Power Apps](https://docs.microsoft.com/powerapps/getting-started) är en bra utgångspunkt om du inte har använt Power Apps förut.

När du är klar att bädda in en viss app kan du välja mellan ett av två sätt för att komma åt app på sidan, oavsett vilken väg som bättre passar ditt scenario. Det första sättet är via knappen Power Apps som har lagts till i standardåtgärdsfönstret. Appar som läggs till med den här funktionen visas som menyobjekt inne i menyknappen Power Apps. När den väljs kommer var och en av dessa menyobjekt att öppna en sidoruta som innehåller inbäddade app. Alternativt kan du visa en inbäddad app direkt på en sida som en ny flik, snabbflik, blad eller ett nytt avsnitt på en arbetsyta.

När du konfigurerar din inbäddade app kan du välja ett fält som du vill skicka som kontext till app. På så sätt kan app svara utifrån den information som för närvarande visas.

### <a name="details"></a>Detaljer

Följande instruktioner visar hur du bäddar in en en app från Power Apps i webbklienten.

1. Gå till sidan där du vill bädda in appen. Detta är samma sida som innehåller alla data som ska skickas till appen som indata.
2. Öppna fönstret **Lägg till en app från Power Apps**:

    - Klicka på **Alternativ** och välj **Anpassa den här sidan**. Under menyn **Infoga** väljer du **Power Apps**. Slutligen kan du välja den region där du vill lägga till appen. Om du vill bädda in appen under menyknappen Power Apps väljer du åtgärdsfönstret. Om du vill bädda in appen direkt på sidan, välj lämplig flik, snabbflik, blad eller avsnitt (om du är på en arbetsyta).
    - Om appen sker med hjälp av menyknappen Power Apps, klickar du alternativt på menyn **Power Apps** i standardåtgärdsfönstret och väljer sedan **Lägg till en app**.

3. Konfigurera inbäddade appen:

    - Fältet **Namn** indikerar texten som visas för knappen eller fliken som innehåller inbäddade appen. Du kanske ofta vill upprepa namnet på appen i det här fältet.
    - **Program-ID** är GUID för appen som du vill bädda in. För att hämta det här värdet hittar du appen på [web.powerapps.com](https://web.powerapps.com) och letar sedan upp den i fältet **Program-ID** under **Uppgifter**.
    - För **Mata in kontext för appen**, kan du även välja fältet som innehåller de data som du vill skicka till appen som indata. Se avsnittet längre fram i det här ämnet med namnet [Bygga appar som använder data från Finance and Operations-appar](#building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps) för information om hur appen kan komma åt data som skickas från Finance and Operations-appar.
    - Välj **Programstorlek** som matchar typen av app som du bäddar in. Välj **Tunn** för appar som har skapats för mobila enheter och **Omfattande** för appar som skapats för surfplattor. Detta säkerställer att en tillräcklig mängd utrymme avsätts för inbäddade appen.
    - Snabbfliken **Juridiska personer** innehåller möjligheten att välja vilka juridiska personer som appen är tillgänglig för. Standard är att visa appen för alla juridiska personer. Det här alternativet är bara tillgängligt om funktionen [sparade vyer](saved-views.md) är inaktiverad. 

4. När du har bekräftat att konfigurationen är korrekt klickar du på **Infoga** för att bädda in PowerApp på sidan. Du uppmanas att uppdatera webbläsaren för att kunna visa inbäddade app.

## <a name="sharing-an-embedded-app"></a>Dela en inbäddad app

När du har bäddat in en app på en sida och bekräftat att den fungerar korrekt med all datakontext som skickas från sidan, kanske du vill dela denna med andra användare i systemet. Det kan du göra på två olika sätt genom att använda funktionerna för anpassning av produkten:

- Det rekommenderade scenariot är via den systemadministratör som kan skicka en anpassning till alla användare eller en grupp användare.
- Du kan också exportera din sidas anpassningar, skicka dem till en eller flera användare och låta var och en av dessa användare importera ändringarna. Verktygsfältet för anpassning har åtgärder som gör att du kan exportera och importera anpassningar.

Se [Anpassa användarupplevelsen](personalize-user-experience.md) för mer information om anpassningsfunktionerna i produkten och hur de används.

## <a name="building-an-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Skapa en app som använder data som skickas från Finance and Operations-appar

En viktig del i skapandet av en app från Power Apps som bäddas in i en Finance and Operations-app använder indata från det programmet. Från Power Apps utvecklingsmiljön kan du få åtkomst till indata från en Finance and Operations-app med hjälp av variabeln Param("EntityId").

Exempelvis i appens OnStart-funktion kan du ange indata från Finance and Operations-appar till en variabel så här:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-app"></a>Visa en app

Om du vill visa en inbäddad app på en sida i Finance and Operations-appar, gå till en sida med en inbäddad app. Kom ihåg att appar kan nås via knappen Power Apps i åtgärdsfönstret som standardåtgärdsfönster och kan visas direkt på sidan som en ny flik på snabbflik, blad eller som ett nytt avsnitt på en arbetsyta. När en användare först försöker läsa in en app på en sida, uppmanas han eller hon att logga in för att säkerställa att användaren har behörighet att använda appen.

## <a name="editing-an-embedded-app"></a>Redigera en inbäddad app

När en app har bäddats in på en sida, kan du behöva göra några ändringar av den appkonfigurationen. Exempelvis kanske du vill ändra etiketten som är kopplad till den inbäddade appen eller en ny version av en app har skapats och du behöver uppdatera program-ID som pekar på den senaste.

Gör så här om du vill redigera en inbäddad appkonfiguration:

1. Gå till fönstret **Redigera en app**.

    - Om den inbäddade appen sker via menyknappen Power Apps, högerklicka på menyknappen Power Apps och välj **Anpassa**. Välj den app som du vill konfigurera från listrutan **Välj app**.
    - Om den inbäddade app visas direkt på sidan väljer du **alternativ**, och välj sedan **anpassa den här sidan**. Med hjälp av verktyget **Välj**, klickar du på den inbäddade appen.

2. Gör nödvändiga ändringar i konfigurationen för appen och klicka på **spara**.

## <a name="removing-an-app"></a>Ta bort en app

När en app har inbäddats på en sida finns det två sätt att ta bort den vid behov:

- Gå till fönstret **Redigera en app** med instruktioner från sektionen [redigera en inbäddad app](#editing-an-embedded-power-app) tidigare i det här avsnittet. Bekräfta att fönstret visar information om inbäddade appen som du vill ta bort och klicka på knappen **Ta bort**.
- Eftersom en inbäddad app sparas som anpassningsdata, kommer rensning av sidans anpassningar också att ta bort eventuella inbäddade appen på sidan. Observera att rensa sidans anpassning är permanent och kan inte ångras. Ta bort dina anpassningar på en sida genom att markera **Alternativ** och sedan **Anpassa denna sida** och sedan på knappen **Avmarkera**. När du har uppdaterat din webbläsare raderas alla tidigare anpassningar för den här sidan. Se[Anpassa användarupplevelsen](personalize-user-experience.md) för mer information om hur man optimerar sidor med hjälp av personalisering.

## <a name="appendix"></a>Bilaga

### <a name="developer-control-over-where-an-app-can-be-embedded"></a>Utvecklaren styr där en app kan bäddas in

Som standard kan användare bädda in appar på sidan under menyknappen Power Apps eller direkt på sidan som en flik, snabbflik, blad eller ett nytt avsnitt på en arbetsyta. Emellertid kan utvecklare vid behov även konfigurera funktionen till att endast tillåta inbäddning av appar för vissa sidor genom att använda följande metoder:

- **isPowerAppPersonalizationEnabled** – om den här metoden returnerar falsk för en viss sida kommer menyknappen Power Apps inte att visas och användare kommer inte att bädda in appar på sidan, inklusive som en flik.
- **isPowerAppTabPersonalizationEnabled** - om den här metoden returnerar falsk för en viss sida kan användare inte bädda in appar direkt på sidan som en flik, snabbflik eller panoramasektion. Användare kan fortfarande bädda in appar via menyknappen Power Apps om inbäddning tillåts på sidan.

I följande exempel visas en ny klass för dessa två metoder som behövs för att konfigurera där appar kan bäddas in.

```
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return result;
    }
    
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return result;
    }
}
```
