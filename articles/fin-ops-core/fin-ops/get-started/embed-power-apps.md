---
title: Bädda in arbetsyteapp från Power Apps
description: Det här avsnittet förklarar hur du bäddar in arbetsyteappar från Microsoft Power Apps till klienten för att utöka produktens funktionalitet.
author: jasongre
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 37ef6101a5a69e9c820347dd6f61c987467d40b3
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344539"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Bädda in arbetsyteapp från Power Apps

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Microsoft Power Apps är en tjänst som gör det möjligt för både utvecklare och icke-tekniska användare att skapa anpassade företagsprogram för mobila enheter, surfplattor och webben utan att behöva skriva kod. Finance and Operations-appar stöder integrering med Power Apps. Arbetsyteappar som utvecklas av dig, ditt företag eller det bredare ekosystemet kan bäddas in i Finance and Operations-appar utöka produktens funktioner. Exempelvis kan du skapa en arbetsyteapp från Power Apps som kompletterar en Finance and Operations-app med information som hämtas från ett annat system.

Om du vill veta mer om inbäddning av arbetsyteappar kan du titta på den korta videon [Så här bäddar du in arbetsyteappar](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Lägger till en inbäddad arbetsyteapp från Power Apps på en sida

När du bäddar in en arbetsyteapp från Power Apps till klienten måste du först hitta eller skapa ett programmed önskade bilder eller funktioner. Det här avsnittet innehåller ingen detaljerad beskrivning av processen för att bygga appar. Om Power Apps är nytt för dig, se [Power Apps-dokumentationen](/powerapps/).

Det finns tre sätt att bädda in en arbetsyteapp i en Finance and Operations-app. Du kan använda den metod som passar just ditt scenario bäst. 

- Bädda in arbetsyteappen i **Power Apps**-knappen i standardåtgärdsfönstret på en sida. Program som du lägger till på det här sättet visas som artiklar i **Power Apps**-menyknappen, och programmen öppnas i sidofönster. 
- Bädda in arbetsyteappen direkt på en befintlig sida som en ny fliksida (pivot-flik, snabbflik, blad eller arbetsyta).
- Skapa en ny helsidesupplevelse för arbetsyteappen från instrumentpanelen.

När du konfigurerar din inbäddade arbetsyteapp kan du välja ett fält som du vill skicka som kontext till app. Detta steg gör att appen kan svara utifrån den information som för närvarande visas.

> [!NOTE]
> Du kan inte använda denna mekanism för att bädda in modellbaserade appar.

### <a name="embedding-a-canvas-app-on-an-existing-page"></a>Bädda in en arbetsyteapp på en befintlig sida

Följande procedur visar hur du bäddar in en arbetsyteapp på en befintlig sida från Power Apps.

1. Gå till sidan där du vill bädda in arbetsyteappen. Denna sida innehåller alla data som måste skickas vidare till appen som indata.
2. Öppna fönstret **Lägg till ett program från Power Apps**:

    - Om programmet bäddas in direkt på sidan väljer du **Alternativ** \> **Anpassa denna sida** \> **Mer** och följer sedan ett av dessa steg:

        - Om funktionen **Helsidesappar** har aktiverats väljer du **Lägg till en sida** och väljer sedan den region den region där du vill lägga till programet. Om du vill bädda in programmet i **Power Apps**-menyknappen väljer du åtgärdsfönstret. Om du vill bädda in programmet direkt på sidan väljer du lämplig flik, snabbflik, lämpligt blad eller avsnitt (om du befinner dig på en arbetsyta). I fönstret **Lägg till en app** väljer du sedan **Power Apps**.
        - Om funktionen **Helsidesappar** är avstängd väljer du **Lägg till ett program från Power Apps** och sedan den region där du vill lägga till programmet. Om du vill bädda in programmet i **Power Apps**-menyknappen väljer du åtgärdsfönstret. Om du vill bädda in programmet direkt på sidan väljer du lämplig flik, snabbflik, lämpligt blad eller avsnitt (om du befinner dig på en arbetsyta).

    - Om åtkomst till appen fås via menyknappen **Power Apps** kan du välja menyknappen **Power Apps** i standard-åtgärdsfönstret och sedan **Lägg till en app**.

3. Konfigurera den inbäddade appen. Mer information finns i avsnittet [Konfigurera en arbetsyteapp](#configuring-a-canvas-app) senare i det här avsnittet.
4. När du har bekräftat att konfigurationen är korrekt väljer du **Infoga**.

    - Om funktionen **Sparade vyer** är inaktiverad uppmanas du att uppdatera webbläsaren för att se det inbäddade programmet.
    - Om funktionen **Sparade vyer** har aktiverats måste du spara vyn för att ändringen ska bevaras.

### <a name="embedding-a-canvas-app-as-a-full-page-experience-from-the-dashboard"></a>Bädda in en arbetsyteapp som en helsidesupplevelse från instrumentpanelen

Om programmet inte är relaterat till en befintlig sida, eller om du bara vill ha en helsidesupplevelse för appen inuti Finance and Operations-programmet, bör du bädda in en arbetsyteapp från instrumentpanelen.

> [!NOTE]
> Om du vill göra denna funktion tillgänglig måste du aktivera funktionen **Helsidesappar** i funktionshanteringen. 

1. Öppna instrumentpanelen.
2. Markera och håll ned (eller högerklicka) på sidan, välj **Anpassa** och välj sedan **Lägg till en sida**.
3. I fönstret **Lägg till en sida** väljer du **Power Apps**.
4. Konfigurera den inbäddade appen. Mer information finns i avsnittet [Konfigurera en arbetsyteapp](#configuring-a-canvas-app) senare i det här avsnittet.
5. Välj **Spara** om du vill lägga till programmet i instrumentpanelen som en ny panel.
6. Markera den nya panelen på instrumentpanelen och bekräfta att arbetsyteappen visas som förväntat.

### <a name="configuring-a-canvas-app"></a>Konfigurera en arbetsyteapp

När du bäddar in en arbetsyteapp måste du ställa in följande parametrar:

- **Namn** – Ange den text som ska visas för den knapp eller flik som ska innehålla den inbäddade appen. Ofta kan det vara en bra idé att upprepa namnet på appen i det här fältet.
- **App-ID** – Anger den globala unika identifieraren (GUID) för den arbetsyteapp som du vill bädda in. För att hämta det här värdet hittar du appen på [make.powerapps.com](https://make.powerapps.com) och letar sedan upp den i fältet **Program-ID** under **Detaljer**.
- **Mata in kontext för appen** – Om du vill kan du välja fältet som innehåller de data som du vill skicka till appen som indata. Om du vill veta mer om hur appen får åtkomst till de data som skickas från Finance and Operations-appar går du till avsnittet [Bygga en app som använder data skickad från Finance and Operations-appar](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) längre fram i detta ämne.

    Från och med version 10.0.19 kommer den aktuella juridiska personen också att skickas som kontext till arbetsyteappen med hjälp av URL-parametern **cmp**. Detta beteende påverkar inte målarbetsyteappen förrän den appen använder den informationen.

- **Programstorlek** – Välj den apptyp som du bäddar in. Välj **Tunn** för appar som skapats för mobila enheter, eller **Omfattande** för appar som skapats för surfplattor. Denna parameter säkerställer att en tillräcklig mängd lagringsutrymme avsätts för den inbäddade appen.
- **Juridiska personer** – Du kan välja vilka juridiska personer som programmet ska vara tillgängligt för. Som standard är programmet tillgängligt för alla juridiska personer. Detta alternativ är bara tillgängligt när du arbetar direkt på en befintlig sida och funktionen **[Sparade vyer](saved-views.md)** är inaktiverad.

## <a name="sharing-an-embedded-app"></a>Dela en inbäddad app

När du har bäddat in en arbetsyteapp på en sida och bekräftat att den fungerar korrekt, kanske du vill dela appen med andra användare i systemet. Om du vill dela en inbäddad arbetsyteapp följer du stegen nedan.

1. [Dela arbetsyteappen i Power Apps](/powerapps/maker/canvas-apps/share-app) med lämpliga användare så att dessa får direkt åtkomst till appen i Power Apps.
2. Dela anpassningarna som är associerade med det inbäddade programmet med önskade användare. Du kan använda någon av följande metoder:

    - **Publicera vyn (rekommenderas):** Om funktionen **[Sparade vyer](saved-views.md)** är aktiverad bör du skapa en vy som inkluderar det inbäddade programmet och sedan publicera den vyn för önskade användare. På så sätt ser du till att alla användare som har de säkerhetsroller som är riktade mot den publicerade vyn kommer att se arbetsyteappen på sidan.

        Du kan också publicera en arbetsyteapp som har bäddats in som en helsiderfarenhet från instrumentpanelen. Markera och håll (eller högerklicka) den panel som är kopplad till programmet på instrumentpanelen, välj **Anpassa** och sedan **Publicera sida**. En erfarenhet som liknar *publiceringsvyerna* visas, och du kan välja vilka säkerhetsroller du vill publicera på. Om funktionen **Förbättrat stöd för juridiska personer för sparade vyer** är aktivera kan du från och med version 10.0.21 även publicera appen i önskade juridiska personer.

    - Om funktionen **Sparade vyer** är avstängd kan systemadministratören tillhandahålla en anpassning som inkluderar arbetsyteappen till en lämplig uppsättning arbetare via sidan **Anpassning**. Du kan också exportera sidans anpassningar och sedan skicka dem till en eller flera användare. Var och en av dessa användare kan sedan importera anpassningen. Verktygsfältet för anpassning har knappar som gör att du kan exportera och importera anpassningar.

> [!NOTE]
> Om arbetsyteapp har delats med externa användare kan dessa användare inte använda den inbäddade appen i Finance and Operations-appar. De kan emellertid komma åt appen direkt i Power Apps. Externa användare inkluderar gäster och användare som inte tillhör den Microsoft 365 Azure-katalog där Finance and Operations-appen distribueras.

Se [Anpassa användarupplevelsen](personalize-user-experience.md) för mer information om anpassningsfunktionerna i produkten och hur de används.

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Skapa en arbetsyteappen som använder data som skickas från Finance and Operations-appar

När du skapar en arbetsyteappen som ska bäddas in i en Finance and Operations-app, är en viktig del av processen att använda indata från den Finance and Operations-appen. Från Power Apps utvecklingsmiljön kan du få åtkomst till indata från en Finance and Operations-app med hjälp av variabeln **Param("EntityId")**. Från och med version 10.0.19 kommer den aktuella juridiska personen dessutom även att skickas arbetsyteappen med hjälp av variabeln **Param("cmp")**. 

Exempelvis i appens OnStart-funktion kan du ange indata från Finance and Operations-appar till en variabel så här:

``` Power Apps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));

If(!IsBlank(Param("cmp")), Set(FinOpsLegalEntity, Param("cmp")), Set(FinOpsLegalEntity, ""));
```

## <a name="viewing-a-canvas-app"></a>Visa en arbetsyteapp

Om du vill visa en inbäddad arbetsyteapp på en sida i Finance and Operations-appar, gå till en sida med en inbäddad app. Kom ihåg att appar kan nås genom att använda **Power Apps**-knappen i standard åtgärdsfönstret. Alternativt kan de visas direkt på sidan som en ny flik, snabbflik, blad eller ett nytt avsnitt på en arbetsyta. När användarna först försöker läsa in ett programpå en sida uppmanas han eller hon att logga in. Det här steget ser till att användarna har rätt behörighet för att använda appen.

## <a name="editing-an-embedded-app"></a>Redigera en inbäddad app

När ett program har bäddats in på en sida, kan du behöva göra några ändringar av den appkonfigurationen. Exempelvis kanske du vill ändra etiketten som är kopplad till den inbäddade appen eller en ny version av ett program har skapats och du behöver uppdatera program-ID som pekar på den senaste.

Gör så här om du vill redigera en inbäddad appkonfiguration:

1. Gå till fönstret **Redigera en app**.

    - Om åtkomst till den inbäddade appen sker via menyknappen för Power Apps väljer och håller du menyknappen Power Apps intryckt (eller högerklickar på den) och väljer **Anpassa**. Välj dett programsom du vill konfigurera från listrutan **Välj app**.
    - Om den inbäddade app visas direkt på sidan väljer du **alternativ**, och välj sedan **anpassa den här sidan**. Med hjälp av verktyget **Välj**, klickar du på den inbäddade appen.
    - Om det inbäddade programmet har lagts till från instrumentpanelen öppnar du instrumentpanelen, markerar och håller ned (eller högerklickar) på den panel som är kopplad till appen, väljer **Anpassa** och sedan **Redigera sida**.

2. Gör nödvändiga ändringar i konfigurationen för appen och klicka på **spara**.

## <a name="removing-an-app"></a>Ta bort en app

När en app har bäddats in på en sida finns det några olika sätt att ta bort den vid behov:

- Gå till fönstret **Redigera en app** med instruktioner från sektionen [redigera en inbäddad app](#editing-an-embedded-app) tidigare i det här avsnittet. Bekräfta att fönstret visar information om inbäddade appen som du vill ta bort och klicka på knappen **Ta bort**.
- Om det inbäddade programmet har lagts till från instrumentpanelen öppnar du instrumentpanelen, markerar och håller ned (eller högerklickar) på den panel som är kopplad till arbetsyteappen, väljer **Anpassa** och sedan **Ta bort sida**. 
- Eftersom en inbäddad app sparas som anpassningsdata, kommer rensning av sidans anpassningar också att ta bort eventuella inbäddade appen på sidan. Observera att rensa sidans anpassning är permanent och kan inte ångras. Ta bort dina anpassningar på en sida genom att markera **Alternativ** och sedan **Anpassa denna sida** och sedan på knappen **Avmarkera**. När du har uppdaterat din webbläsare raderas alla tidigare anpassningar för den här sidan. Se[Anpassa användarupplevelsen](personalize-user-experience.md) för mer information om hur man optimerar sidor med hjälp av personalisering.

## <a name="appendix"></a>Bilaga

### <a name="developer-modeling-a-canvas-app-on-a-form"></a>[Utvecklare] Basera en arbetsyteapp på ett formulär

Även om det här ämnet fokuserar på att bädda in arbetsyteappar genom anpassning har utvecklarna också möjlighet att lägga till en arbetsyteapp i ett formulär med hjälp av utvecklingsupplevelsen Visual Studio. Detta gör du genom att helt enkelt lägga till en PowerAppsHostControl i formuläret. Metadataegenskaperna som finns i kontrollen ger samma funktioner som anpassningsupplevelsen.

### <a name="developer-specifying-where-an-app-can-be-embedded"></a>[Utvecklare] ange var ett programkan bäddas in

Som standard kan användare bädda in appar på sidan under menyknappen Power Apps eller direkt på sidan som en flik, snabbflik, blad eller ett nytt avsnitt på en arbetsyta. Emellertid kan utvecklare vid behov även konfigurera funktionen till att endast tillåta inbäddning av appar för vissa sidor genom att använda följande metoder:

- **isPowerAppPersonalizationEnabled** – om den här metoden returnerar falsk för en viss sida kommer menyknappen Power Apps inte att visas och användare kommer inte att bädda in appar på sidan, inklusive som en flik.
- **isPowerAppTabPersonalizationEnabled** – om den här metoden returnerar falsk för en viss sida kan användare inte bädda in appar direkt på sidan som en flik, snabbflik eller panoramasektion. Användare kan fortfarande bädda in appar via menyknappen Power Apps om inbäddning tillåts på sidan.

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
