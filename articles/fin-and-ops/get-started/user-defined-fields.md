---
title: Skapa och arbeta med anpassade fält
description: Det här avsnittet visar hur Microsoft Dynamics 365 for Finance and Operations tillåter vissa användare att skapa egna fält för att anpassa programmet så att det passar verksamheten.
author: jasongre
manager: AnnBe
ms.date: 07/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 18402579789c17de7b46dd7a013b3b6327ea5d4f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "348030"
---
# <a name="create-and-work-with-custom-fields"></a>Skapa och arbeta med anpassade fält

[!include [banner](../includes/banner.md)]

Trots att Microsoft Dynamics 365 for Finance and Operations ger en omfattande uppsättning av färdiga fält för hantering av en mängd olika affärsprocesser, kan ibland företag ha behov av att söka ytterligare information i systemet. För att tillgodose detta behov tillåter Finance and Operations dig att skapa egna fält för att anpassa programmet så att det passar ditt företag, förutsatt att du har behörighet till funktionen.

Möjligheten att lägga till egna fält finns i plattformsuppdatering 13 och senare.

Det här videoklippet visar hur enkelt det är att lägga till ett anpassat fält på en sida: [Lägga till anpassade fält i Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=gWSGZI9Vtnc).

## <a name="creating-custom-fields"></a>Skapa anpassade fält

När du har identifierat ytterligare information som du vill spåra i programmet skapar du anpassade fält i lämplig tabell och visar det nya fältet på en sida.

Följande steg beskriver processen för att skapa ett anpassat fält och placera fältet i ett formulär.

1. Navigera till det formulär där det nya fältet behövs.
2. Eftersom slutmålet är att tillhandahålla anpassade fält i ett formulär, finns startpunkten för att skapa anpassade fält i anpassningserfarenheten. Öppna verktygsfältet för att anpassa genom att välja **alternativ**, och sedan **anpassa formuläret**.
3. Klicka på **infoga** och **fält**.
4. Välj det område på formuläret där du vill visa det nya fältet. När du valt område visar dialogrutan **Infoga fält** en lista över befintliga fält som kan infogas i det markerade området på formuläret.
5. Kontrollera att det fält du är intresserad av inte redan finns i listan. Om det gör det markerar du bara fältet i listan och klickar på **infoga**.
6. Klicka på knappen **Skapa nytt fält** ovanför listan för att initiera processen att skapa ett anpassat fält. Då öppnas dialogrutan **Skapa nytt fält**.

    Om du inte ser knappen **Skapa nytt fält** har du inte behörighet att använda den här funktionen.

7. Ange följande information i dialogrutan **Skapa nytt fält**.

    1. Markera databastabellen där fältet ska läggas till. Observera att bara de tabeller som har stöd för anpassade fält visas i rullgardinsmenyn. Se avsnittet nedan för teknisk information om tabeller som stöds.
    2. Välj datatyp för det nya fältet. Tillgängliga datatyper är kryssruta, datum, datum/tid, decimal, nummer, plocklista och text.

        - Om du väljer datatypen text kan du också ange maxlängden för den text som kan skrivas in i fältet.
        - Om du väljer datatypen plocklista kan du också välja en uppsättning giltiga värden för fältet.

    3. Ange namn, etikett och hjälptext för fältet. Namnet motsvarar det fysiska fältnamnet i databasen, där etikett och hjälptext används för att representera fältet i användargränssnittet.

8. Om detta är det enda fält du måste skapa för det här formuläret klickar du på **spara**. Om du behöver skapa ytterligare fält klickar du på **spara och skapa ny** och går tillbaka till steg 7. Observera att det finns en gräns på **20 anpassade fält per tabell**.
9. När du lämnar dialogrutan **Skapa nytt fält** kommer du automatiskt tillbaka till dialogrutan **Infoga fält**. Fält som nyss lagts till markeras automatiskt i listan över fält som ska infogas i formuläret.
10. Klicka på **infoga** för att infoga markerade fält i det utvalda området på formuläret.
11. **Valfritt:** Aktivera läget **flytta** från verktygsfältet för anpassning för att flytta de nya fälten till önskad plats i det markerade området. Se [anpassa användarupplevelsen](personalize-user-experience.md) för mer information om hur du använder olika funktioner för anpassning om du vill optimera ett formulär för din personliga användning.

## <a name="sharing-custom-fields-with-other-users"></a>Dela anpassade fält med andra användare

När du har skapat ett anpassat fält och det visas i ett formulär, vill du kanske tillhandahålla denna uppdaterade sida som innehåller det nya fältet för andra användare i systemet. Det kan du göra på två olika sätt genom att använda funktionerna för anpassning av produkten:

- Det rekommenderade flödet är via den systemadministratör som kan skicka en anpassning till alla användare eller en grupp användare. Mer information i [Anpassa användarupplevelsen](personalize-user-experience.md).
- Du kan också exportera dina ändringar (kallas *anpassningar*), skicka dem till en eller flera användare och låta var och en av dessa användare importera ändringarna. Alternativet **hantera** verktygsfältet för anpassning låter dig exportera och importera anpassningar.

## <a name="managing-custom-fields"></a>Hantera anpassade fält

Hanteringen av anpassade fält i systemet kan utföras via sidan **anpassade fält** i modulen systemadministration. Den här sidan ger användare tillgång till många funktioner, inklusive:

- Visa en lista över alla anpassade fält i systemet.
- Begränsad redigering av befintliga anpassade fält.
- Radera anpassade fält.
- Visa anpassade fält i datatabeller.
- Tillhandahålla översättningar av etiketter och hjälptexter till anpassade fält.

### <a name="viewing-all-custom-fields"></a>Visa alla anpassade fält

Sidan **anpassade fält** visar alla anpassade fält som har definierats i systemet. Välj den tabell som du är intresserad av och sidan uppdateras för att visa en lista över de anpassade fält som är kopplade till tabellen. Genom att välj ett anpassat fält i listan kan du se alla detaljer om fältet.

### <a name="editing-custom-fields"></a>Redigera anpassade fält

När du har skapat ett anpassat fält kan bara vissa delar av information om det anpassade fältet ändras på sidan **anpassade fält**.

Du *kan* ändra dessa attribut:

- Etikett
- Hjälptext
- Längden, på textfält

Du kan *inte* redigera följande attribut:

- Fältnamn
- Datatyp

För plocklista kan dessutom uppsättningen av giltiga värden för anpassade fält ordnas om och nya värden kan läggas till, befintliga värden för fältet plocklista kan dock inte tas bort. Kom ihåg att klicka på **verkställ ändringarna** när du är klar med redigeringen av fält för en viss tabell för att spara ändringarna.

### <a name="exposing-custom-fields-on-data-entities"></a>Visa anpassade fält i datatabeller

Det kan också vara viktigt att visa anpassade fält i datatabeller. Datatabeller används i funktionen [Öppna i Office](../../dev-itpro/office-integration/office-integration.md) samt vid import och export av data.

Gör så här om du vill visa ett anpassat fält i en datatabell:

1. Välj anpassade fält i formuläret **anpassade fält**.
2. Expandera avsnittet **enheter** för att visa uppsättningen av relevanta enheter.
3. Klicka på knappen för att **redigera**.
4. Ändra fältet **aktiverad** för varje enhet som ska visas i det här fältet.
5. Spara ändringarna genom att klicka på **Spara ändringar**.

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a>Tillåra anpassade fält att visas på ett annat språk

Eftersom anpassade fält kan behöva användas av användare på en mängd språk, måste sidan **anpassade fält** ge dig möjlighet att översätta etikett och hjälptext till andra språk.

Följande steg beskriver processen för översättning av anpassade fält till ett annat språk:

1. Välj det anpassade fältet på sidan **anpassade fält**.
2. Välj knappen **Översättningar** i åtgärdsfönstret. Då öppnas en rullgardinsmeny med befintliga transaktioner för det här fältet.
3. Rullgardinsmenyn **språk** visar vilka språk som det redan finns översättningar för.

    Om du vill redigera en befintlig översättning väljer du önskat språk på menyn och ändrar värdena etiketten och hjälptext.

    Annars klickar du på **lägga till språk** och välj språk i menyn. Översätt sedan etikett och hjälptext.

4. Klicka på **OK**, när du är klar.

### <a name="deleting-custom-fields"></a>Radera anpassade fält

I sällsynta fall kanske du bestämmer att ett anpassat fält inte längre behövs. I dessa fall kan systemadministratören välja att ta bort fältet från sidan **anpassade fält**. Kontrollera att rätt fält är markerat, klicka du på **ta bort** och sedan på **ja** för att att bekräfta borttagningen och klicka slutligen på **verkställ ändringar**.

> [!NOTE]
> Den här åtgärden kan inte ångras och innebär att data som hör till fältet tas bort permanent från databasen.

## <a name="appendix"></a>Bilaga

### <a name="who-can-create-custom-fields"></a>Vem kan skapa anpassade fält?

För att skydda systemet kan, som standard, endast systemadministratörer skapa anpassade fält. Men de privilegierade användare som organisationen anser nödvändiga kan få behörighet att skapa anpassade fält av en systemadministratör med hjälp av säkerhetsrollen **körning anpassning privilegierad användare**. Användare utan den här säkerhetsrollen kommer inte att kunna skapa anpassade fält, men kommer fortfarande att kunna se och använda anpassade fält som lagts till av andra användare i systemet.

### <a name="what-tables-support-custom-fields"></a>Vilka tabeller har stöd för anpassade fält?

Av prestandaskäl och tekniska skäl kan för tillfället endast tabeller som uppfyller följande villkor tillåta att anpassade fält läggs till.

- Tabellen måste vara märkas som en av dessa grupper:

    - Grupp
    - WorksheetHeader
    - Rubrik
    - Diverse
    - Parameter
    - Referens
    - TransactionHeader

- Tabellen kan inte utöka en annan tabell.
- Registret kan inte klassas som ett systemregister.
- Registret kan inte vara ett tillfälligt register.
