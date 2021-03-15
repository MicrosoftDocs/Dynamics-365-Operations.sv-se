---
title: Bädda in arbetsyteapp från Power Apps
description: Det här avsnittet förklarar hur du bäddar in arbetsyteappar från Microsoft Power Apps till klienten för att utöka produktens funktionalitet.
author: jasongre
manager: AnnBe
ms.date: 11/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: fbdd4dd1bb0b850319b12e55b0e68d6fdc516ad6
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798387"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Bädda in arbetsyteapp från Power Apps

[!include [banner](../includes/banner.md)]

Microsoft Power Apps är en tjänst som gör det möjligt för både utvecklare och icke-tekniska användare att skapa anpassade företagsprogram för mobila enheter, surfplattor och webben utan att behöva skriva kod. Finance and Operations-appar stöder integration med Power Apps. Arbetsyteappar som utvecklas av dig, ditt företag eller det bredare ekosystemet kan bäddas in i Finance and Operations-appar utöka produktens funktioner. Exempelvis kan du skapa en arbetsyteapp från Power Apps som kompletterar en Finance and Operations-app med information som hämtas från ett annat system.

Om du vill veta mer om inbäddning av Power Apps kan du titta på den korta videon [Så här bäddar du in Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Lägger till en inbäddad arbetsyteapp från Power Apps på en sida

### <a name="overview"></a>Översikt

När du bäddar in en arbetsyteapp från Power Apps till klienten måste du först hitta eller skapa en app med önskade bilder eller funktioner. Det här avsnittet innehåller ingen detaljerad beskrivning av processen för att bygga appar. Om Power Apps är nytt för dig, se [Power Apps-dokumentationen](https://docs.microsoft.com/powerapps/).

Det finns två sätt att få åtkomst till en viss arbetsyteapp på en sida när du är redo att bädda in appen. Du kan välja vilken metod som passar ditt scenario bättre. Den första metoden använder knappen **Power Apps** som har lagts till i standardåtgärdsfönstret. Appar som du lägger till genom att använda den här metoden visas som objekt på menyknappen **Power Apps**. När du väljer ett av dessa objekt visas en sidoruta som innehåller inbäddade app. Alternativt kan du visa en inbäddad app direkt på en sida som en ny flik, snabbflik, blad eller ett nytt avsnitt på en arbetsyta.

När du konfigurerar din inbäddade arbetsyteapp kan du välja ett fält som du vill skicka som kontext till app. Detta steg gör att appen kan svara utifrån den information som för närvarande visas.

> [!NOTE]
> Du kan för närvarande inte använda den här mekanismen för att bädda in modellerade appar.  

### <a name="details"></a>Information

Följande procedur visar hur du bäddar in en arbetsyteapp från Power Apps i webbklienten.

1. Gå till sidan där du vill bädda in arbetsyteappen. Denna sida är samma sida som innehåller alla data som måste skickas till appen som indata.
2. Öppna fönstret **Lägg till en app från Power Apps**:

    - Klicka på **Alternativ** och välj **Anpassa den här sidan**. Under menyn **Infoga** väljer du **Power Apps**. Slutligen kan du välja den region där du vill lägga till appen. Om du vill bädda in appen under menyknappen Power Apps väljer du åtgärdsfönstret. Om du vill bädda in appen direkt på sidan, välj lämplig flik, snabbflik, blad eller avsnitt (om du är på en arbetsyta).
    - Om appen sker med hjälp av menyknappen Power Apps, klickar du alternativt på menyn **Power Apps** i standardåtgärdsfönstret och väljer sedan **Lägg till en app**.

3. Konfigurera inbäddade appen:

    - Fältet **Namn** indikerar texten som visas för knappen eller fliken som innehåller inbäddade appen. Du kanske ofta vill upprepa namnet på appen i det här fältet.
    - Fältet **App-ID** anger den globala unika identifieraren (GUID) för den arbetsyta som du vill bädda in. För att hämta det här värdet hittar du appen på [make.powerapps.com](https://make.powerapps.com) och letar sedan upp den i fältet **Program-ID** under **Detaljer**.
    - För **Mata in kontext för appen**, kan du även välja fältet som innehåller de data som du vill skicka till appen som indata. Se avsnittet längre fram i det här ämnet med namnet [Bygga appar som använder data från Finance and Operations-appar](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) för information om hur appen kan komma åt data som skickas från Finance and Operations-appar.
    - Välj **Programstorlek** som matchar typen av app som du bäddar in. Välj **Tunn** för appar som har skapats för mobila enheter och **Omfattande** för appar som skapats för surfplattor. Detta säkerställer att en tillräcklig mängd utrymme avsätts för inbäddade appen.
    - Snabbfliken **Juridiska personer** innehåller möjligheten att välja vilka juridiska personer som appen är tillgänglig för. Standard är att visa appen för alla juridiska personer. Det här alternativet är bara tillgängligt om funktionen [sparade vyer](saved-views.md) är inaktiverad. 

4. När du har bekräftat att konfigurationen är korrekt klickar du på **Infoga** för att bädda in PowerApp på sidan. Du uppmanas att uppdatera webbläsaren för att kunna visa inbäddade app.

## <a name="sharing-an-embedded-app"></a>Dela en inbäddad app

När du har bäddat in en arbetsyteapp på en sida och bekräftat att den fungerar korrekt med all datakontext som skickas från sidan, kanske du vill dela appen med andra användare i systemet. Om du vill dela en inbäddad arbetsyteapp följer du stegen nedan.

1. [Dela arbetsyteappen](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) med rätt användare så att de kan komma åt appen i Power Apps. 

2. Se till att de målinriktade användarna har lämpliga anpassningar, så att den inbäddade appen visas när dessa användare visar sidan. Du kan använda någon av följande metoder:

    - Rekommenderas: Använd funktionen [Sparade vyer](saved-views.md) för att skapa och publicera en vy som innehåller den inbäddade appen. På så sätt ser du till att alla användare som har de säkerhetsroller som är riktade mot den publicerade vyn kommer att se appen i Finance and Operations-appar. 
    - Om du inte har aktiverat funktionen Sparade vyer kan du låta system administratören sända en anpassning som innehåller den inbäddade appen till alla användare eller en delmängd av användarna. Du kan också exportera sidans anpassningar och skicka dem till en eller flera användare. Var och en av dessa användare kan sedan importera anpassningarna. Verktygsfältet för anpassning har åtgärder som gör att du kan exportera och importera anpassningar. 
    
> [!NOTE]
> Om arbetsyteapp har delats med externa användare kan dessa användare inte använda den inbäddade appen i Finance and Operations-appar. De kan emellertid komma åt appen direkt i Power Apps. Externa användare inkluderar gäster och användare som inte tillhör den Microsoft 365 Azure-katalog där Finance and Operations-appen distribueras.

Se [Anpassa användarupplevelsen](personalize-user-experience.md) för mer information om anpassningsfunktionerna i produkten och hur de används.

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Skapa en arbetsyteappen som använder data som skickas från Finance and Operations-appar

När du skapar en arbetsyteappen som ska bäddas in i en Finance and Operations-app, är en viktig del av processen att använda indata från den Finance and Operations-appen. Från Power Apps utvecklingsmiljön kan du få åtkomst till indata från en Finance and Operations-app med hjälp av variabeln **Param("EntityId")**.

Exempelvis i appens OnStart-funktion kan du ange indata från Finance and Operations-appar till en variabel så här:

```powerapps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-a-canvas-app"></a>Visa en arbetsyteapp

Om du vill visa en inbäddad arbetsyteapp på en sida i Finance and Operations-appar, gå till en sida med en inbäddad app. Kom ihåg att appar kan nås genom att använda **Power Apps**-knappen i standard åtgärdsfönstret. Alternativt kan de visas direkt på sidan som en ny flik, snabbflik, blad eller ett nytt avsnitt på en arbetsyta. När användarna först försöker läsa in en app på en sida uppmanas han eller hon att logga in. Det här steget ser till att användarna har rätt behörighet för att använda appen.

## <a name="editing-an-embedded-app"></a>Redigera en inbäddad app

När en app har bäddats in på en sida, kan du behöva göra några ändringar av den appkonfigurationen. Exempelvis kanske du vill ändra etiketten som är kopplad till den inbäddade appen eller en ny version av en app har skapats och du behöver uppdatera program-ID som pekar på den senaste.

Gör så här om du vill redigera en inbäddad appkonfiguration:

1. Gå till fönstret **Redigera en app**.

    - Om den inbäddade appen sker via menyknappen Power Apps, högerklicka på menyknappen Power Apps och välj **Anpassa**. Välj den app som du vill konfigurera från listrutan **Välj app**.
    - Om den inbäddade app visas direkt på sidan väljer du **alternativ**, och välj sedan **anpassa den här sidan**. Med hjälp av verktyget **Välj**, klickar du på den inbäddade appen.

2. Gör nödvändiga ändringar i konfigurationen för appen och klicka på **spara**.

## <a name="removing-an-app"></a>Ta bort en app

När en app har inbäddats på en sida finns det två sätt att ta bort den vid behov:

- Gå till fönstret **Redigera en app** med instruktioner från sektionen [redigera en inbäddad app](#editing-an-embedded-app) tidigare i det här avsnittet. Bekräfta att fönstret visar information om inbäddade appen som du vill ta bort och klicka på knappen **Ta bort**.
- Eftersom en inbäddad app sparas som anpassningsdata, kommer rensning av sidans anpassningar också att ta bort eventuella inbäddade appen på sidan. Observera att rensa sidans anpassning är permanent och kan inte ångras. Ta bort dina anpassningar på en sida genom att markera **Alternativ** och sedan **Anpassa denna sida** och sedan på knappen **Avmarkera**. När du har uppdaterat din webbläsare raderas alla tidigare anpassningar för den här sidan. Se[Anpassa användarupplevelsen](personalize-user-experience.md) för mer information om hur man optimerar sidor med hjälp av personalisering.

## <a name="appendix"></a>Bilaga

### <a name="developer-specifying-where-an-app-can-be-embedded"></a>[Utvecklare] ange var en app kan bäddas in

Som standard kan användare bädda in appar på sidan under menyknappen Power Apps eller direkt på sidan som en flik, snabbflik, blad eller ett nytt avsnitt på en arbetsyta. Emellertid kan utvecklare vid behov även konfigurera funktionen till att endast tillåta inbäddning av appar för vissa sidor genom att använda följande metoder:

- **isPowerAppPersonalizationEnabled** – om den här metoden returnerar falsk för en viss sida kommer menyknappen Power Apps inte att visas och användare kommer inte att bädda in appar på sidan, inklusive som en flik.
- **isPowerAppTabPersonalizationEnabled** - om den här metoden returnerar falsk för en viss sida kan användare inte bädda in appar direkt på sidan som en flik, snabbflik eller panoramasektion. Användare kan fortfarande bädda in appar via menyknappen Power Apps om inbäddning tillåts på sidan.

I följande exempel visas en ny klass för dessa två metoder som behövs för att konfigurera där appar kan bäddas in.

```powerapps
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]