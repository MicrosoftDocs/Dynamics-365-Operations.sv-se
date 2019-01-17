---
title: "Bädda in PowerApps-program"
description: "Det här avsnittet beskriver hur du bäddar in PowerApps till Finance and Operations-klienten för att utöka produktens funktionalitet."
author: jasongre
manager: AnnBe
ms.date: 09/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.translationtype: HT
ms.sourcegitcommit: 3ee5334c87b2b0acae2afa6882feca63e3b9cc8e
ms.openlocfilehash: 262d34cbc50251595d22c27387fbd3f1045d1fbb
ms.contentlocale: sv-se
ms.lasthandoff: 12/18/2018

---

# <a name="embed-powerapps-apps"></a>Bädda in PowerApps-program

[!include [banner](../includes/banner.md)]

I plattformsuppdatering 14 stöder Microsoft Dynamics 365 for Finance and Operations integrering med Microsoft PowerApps, en tjänst för utvecklare och icke-tekniska användare för att skapa anpassade affärsappar för mobila enheter, surfplattor och webb utan att skriva kod. PowerApps utvecklats av dig, ditt företag eller det bredare ekosystemet och kan sedan bäddas in i Finance and Operations-klienten utöka produktens funktioner. Exempelvis kan du skapa en PowerApp för att komplettera Finance and Operations med information som hämtas från ett annat system.

Om du vill veta mer om inbäddning av PowerApps kan du titta på den korta videon [Så här bäddar du in PowerApps i Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-powerapp-to-a-page"></a>Lägger till en inbäddad PowerApp på en sida

### <a name="overview"></a>Översikt

När du infogar en PowerApp till Finance and Operations-klienten måste du först hitta eller skapa en PowerApp med önskade bilder och/eller funktioner. Vi kommer inte att beskriva den detaljerade processen för att bygga en PowerApp här. Ämnet [Introduktion till PowerApps](https://docs.microsoft.com/powerapps/getting-started) är en bra utgångspunkt om du inte har använt PowerApps förut.

När du är klar att bädda in en viss PowerApp kan du välja mellan ett av två sätt för att komma åt PowerApp på sidan, oavsett vilken väg som bättre passar ditt scenario. Det första sättet är via knappen PowerApps som har lagts till i standardåtgärdsfönstret. PowerApps som läggs till med den här funktionen visas som menyobjekt inne i menyknappen PowerApps. När den väljs kommer var och en av dessa menyobjekt att öppna en sidoruta som innehåller inbäddade PowerApp. Alternativt kan du visa en PowerApp direkt på en sida som en ny flik, snabbflik, blad eller ett nytt avsnitt på en arbetsyta.

När du konfigurerar din inbäddade PowerApp i Finance and Operations kan du välja ett fält som du vill skicka som indata till PowerApp. På så sätt kan PowerApp svara utifrån den information som för närvarande visas i Finance and Operations.

### <a name="details"></a>Detaljer

Följande instruktioner visar hur du bäddar in en PowerApp i webbklienten Finance and Operations.

1. Gå till sidan där du vill bädda in PowerApp. Detta är samma sida som innehåller alla data som ska skickas till PowerApp som indata.
2. Öppna fönstret **Infoga en PowerApp**:

    - Klicka på **Alternativ** och välj **Anpassa det här formuläret**. Under menyn **Infoga** väljer du **PowerApp**. Slutligen kan du välja den region där du vill lägga till PowerApp. Om du vill bädda in PowerApp under menyknappen PowerApps väljer du åtgärdsfönstret. Om du vill bädda in PowerApp direkt på sidan, välj lämplig flik, snabbflik, blad eller avsnitt (om du är på en arbetsyta).
    - Om PowerApp sker med hjälp av menyknappen PowerApps, klickar du alternativt på menyn **PowerApps** i standardåtgärdsfönstret och väljer sedan **infoga en PowerApp**.

3. Konfigurera inbäddade PowerApp:

    - Fältet **Namn** indikerar texten som visas för knappen eller fliken som innehåller inbäddade PowerApp. Du kanske ofta vill upprepa namnet på PowerApp i det här fältet.
    - **Program-ID** är GUID för PowerApp som du vill bädda in. För att hämta det här värdet hittar du PowerApp på [web.powerapps.com](https://web.powerapps.com) och letar sedan upp den i fältet **Program-ID** under **Uppgifter**.
    - För **Mata in data för PowerApp**, kan du även välja fältet som innehåller de data som du vill skicka till PowerApp som indata. Se avsnittet längre fram i det här ämnet med namnet [Bygga en PowerApp som använder data från Finance and Operations](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations) för information om hur PowerApp kan komma åt data som skickas från Finance and Operations.
    - Välj **Programstorlek** som matchar typen av PowerApp som du bäddar in. Välj **Tunn** för PowerApps som har skapats för mobila enheter och **Omfattande** för PowerApps som skapats för surfplattor. Detta säkerställer att en tillräcklig mängd utrymme avsätts för inbäddade PowerApp.
    - Snabbfliken **Juridiska personer** innehåller möjligheten att välja vilka juridiska personer som PowerApp är tillgänglig för. Standard är att visa PowerApp för alla juridiska personer.

4. När du har bekräftat att konfigurationen är korrekt klickar du på **Infoga** för att bädda in PowerApp på sidan. Du uppmanas att uppdatera webbläsaren för att kunna visa inbäddade PowerApp.

## <a name="sharing-an-embedded-powerapp"></a>Dela en inbäddad PowerApp

När du har bäddat in en PowerApp på en sida och bekräftat att den fungerar korrekt med all datakontext som skickas från sidan, kanske du vill dela denna inbäddade PowerApp med andra användare i systemet. Det kan du göra på två olika sätt genom att använda funktionerna för anpassning av produkten:

- Det rekommenderade scenariot är via den systemadministratör som kan skicka en anpassning till alla användare eller en grupp användare.
- Du kan också exportera din sidas anpassningar, skicka dem till en eller flera användare och låta var och en av dessa användare importera ändringarna. Alternativet hantera verktygsfältet för anpassning låter dig exportera och importera anpassningar.

Se [Anpassa användarupplevelsen](personalize-user-experience.md) för mer information om anpassningsfunktionerna i produkten och hur de används.

## <a name="building-a-powerapp-that-leverages-data-sent-from-finance-and-operations"></a>Bygga en PowerApp som innehåller data som skickas från Finance and Operations

En viktig del av att skapa en PowerApp bäddas in i Finance and Operations och använder indata från Finance and Operations. Inuti PowerApp som indata kan användas med variabeln Param("EntityId").

Exempelvis i PowerApp OnStart-funktion kan du ange indata från Finance and Operations till en variabel så här:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-embedded-powerapp"></a>Visa en inbäddad PowerApp

Om du vill visa en inbäddad PowerApp på en sida i Finance and Operations, gå till en sida med en inbäddad PowerApp. Kom ihåg att PowerApps kan nås via knappen PowerApps i åtgärdsfönstret som standardåtgärdsfönster och kan visas direkt på sidan som en ny flik på snabbflik, blad eller som ett nytt avsnitt på en arbetsyta. När en användare först försöker läsa in en PowerApp på en sida, uppmanas han eller hon att logga in på PowerApps för att säkerställa att användaren har behörighet att använda PowerApp.

## <a name="editing-an-embedded-powerapp"></a>Redigera en inbäddad PowerApp

När en PowerApp har bäddats in på en sida, kan du behöva göra några ändringar av den PowerApp-konfigurationen. Exempelvis kanske du vill ändra etiketten som är kopplad till den inbäddade PowerApp eller en ny version av en PowerApp har skapats och du behöver uppdatera program-ID som pekar på den senaste PowerApp.

Gör så här om du vill redigera en inbäddad PowerApp konfiguration:

1. Gå till fönstret **Redigera en PowerApp**.

    - Om den inbäddade PowerApp sker via menyknappen PowerApps, högerklicka på menyknappen PowerApps och välj **Anpassa**. Välj den PowerApp som du vill konfigurera från listrutan **Välj PowerApp**.
    - Om den inbäddade PowerApp visas direkt på sidan väljer du **alternativ**, och välj sedan **anpassa formuläret**. Med hjälp av verktyget **Välj**, klickar du på den inbäddade PowerApp.

2. Gör nödvändiga ändringar i konfigurationen för PowerApps och klicka på **spara**.

## <a name="removing-an-embedded-powerapp"></a>Ta bort en inbäddad PowerApp

När en PowerApp har inbäddats på en sida finns det två sätt att ta bort den vid behov:

- Gå till fönstret **Redigera en PowerApp** med instruktioner från sektionen [redigera en inbäddad PowerApp](#editing-an-embedded-powerapp) tidigare i det här avsnittet. Bekräfta att fönstret visar information om inbäddade PowerApp som du vill ta bort och klicka på knappen **Ta bort**.
- Eftersom en inbäddad PowerApp sparas som anpassningsdata, kommer rensning av sidans anpassningar också att ta bort eventuella inbäddade PowerApps på sidan. Observera att rensa sidans anpassning är permanent och kan inte ångras. Ta bort dina anpassningar på en sida genom att markera **Alternativ** och sedan klicka på **anpassa formuläret**. Under menyn **hantera** väljer du knappen **radera**. När du har uppdaterat din webbläsare raderas alla tidigare anpassningar för den här sidan. Se[Anpassa användarupplevelsen](personalize-user-experience.md) för mer information om hur man optimerar sidor med hjälp av personalisering.

## <a name="appendix"></a>Bilaga

### <a name="developer-control-over-where-a-powerapp-can-be-embedded"></a>Utvecklaren styr där en PowerApp kan bäddas in

Som standard kan användare bädda in PowerApps på sidan under menyknappen PowerApps eller direkt på sidan som en flik, snabbflik, blad eller ett nytt avsnitt på en arbetsyta. Emellertid kan utvecklare vid behov även konfigurera funktionen till att endast tillåta inbäddning av PowerApps för vissa sidor genom att använda följande metoder:

- **isPowerAppersonalizationEnabled** - om den här metoden returnerar falsk för en viss sida kommer menyknappen PowerApps inte att visas och användare kommer inte att bädda in PowerApps på sidan, inklusive som en flik.
- **isPowerAppTabPersonalizationEnabled** - om den här metoden returnerar falsk för en viss sida kan användare inte bädda in PowerApps direkt på sidan som en flik, snabbflik eller panoramasektion. Användare kan fortfarande bädda in PowerApps via menyknappen PowerApps om inbäddning tillåts på sidan.

I följande exempel visas en ny klass för dessa två metoder som behövs för att konfigurera där PowerApps kan bäddas in.

```
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return true;
    }
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return true;
    }
}
```

