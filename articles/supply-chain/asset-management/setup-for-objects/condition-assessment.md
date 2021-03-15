---
title: Villkorsutvärdering
description: Det här avsnittet beskriver hur du skapar en mall för villkorsutvärdering och registrering på en tillgång i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18be786e6f78829f61db1521a923e229fc4f0e70
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021126"
---
# <a name="condition-assessment"></a>Villkorsutvärdering

[!include [banner](../../includes/banner.md)]

 

Det här avsnittet beskriver hur du skapar en mall för villkorsutvärdering och registrering på en tillgång i tillgångshantering. Villkorsutvärdering utförs med jämna mellanrum och det primära målet är att skapa och underhålla villkorsdata för tillgångar. Sett ur ett förebyggande underhållsperspektiv är det viktigt att övervaka viktig information som aktuellt tillstånd och återstående livslängd. Dessutom, om du utför villkorsutvärdering med jämna mellanrum, kommer du att kunna övervaka och jämföra förhållandena på maskinen i din fabrik.

Tillståndsbedömning kan användas för att mäta och övervaka många förhållanden på din utrustning. Exempel: du kan mäta vibrationer på din maskin. När du har registrerat vibrationsmätningar i tillståndshantering på olika typer av utrustning kan du söka efter den senaste registrerade utvärderingen och se vibrationsmätningar.

Villkorsutvärdering skapas på tillgångar. Du ställer in en mall för villkorsutvärdering på en tillgångstyp innan du utför villkors utvärderingsproceduren. Anledningen till att använda mallar för villkorsutvärdering är att undvika variation av villkorsdata på liknande tillgångar. Sekvensen för att ställa in och använda villkorsutvärdering i tillgångshantering är: först ställer du in de nödvändiga villkorsutvärderingsmallarna. Därefter kopplar du mallar med tillgångstyper i formuläret **tillgångstyper**. Slutligen kan du skapa villkorsutvärderingsregistreringar på en tillgång i formuläret **tillgång**.

## <a name="create-a-condition-assessment-template"></a>Skapa en mall för villkorsutvärdering

1. Välj **tillgångshantering** > **inställningar** > **tillgångstyper** > **villkorsutvärdering**.
2. Skapa en ny mall genom att välja **Nytt**.
3. Infoga ID för mallen i fältet **Mall** field.
4. Infoga ett namn för mallen i fältet **Namn**.
5. På snabbfliken **Villkorsutvärderingsrader** lägger du till de rader som krävs för villkorsutvärderingen, inklusive val av lämplig villkorstyp och måttenhet.
6. På snabbfliken **tillgångstyper** lägger du till de tillgångstyper som ska använda mallen för villkorsutvärdering.
7. I fälten **rader** och **tillgångstyper** i gruppen i **detaljgruppen** överst på skärmen ser du antalet utvärderingsrader och tillgångstyper som är relaterade till den valda villkorsutvärderingsmallen.


## <a name="create-condition-assessment-registration-on-an-asset"></a>Skapa villkorsutvärderingsregistrering på en tillgång

1. Välj **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**.
2. I listan väljer du den tillgång du vill skapa en villkorsutvärderingsregistrering för.
3. Klicka på **villkorsutvärdering** på fliken **Allmänt**.
4. Klicka på **Ny** om du vill göra en ny registrering.
5. Välj datum för villkorsutvärderingen i fältet **datum**.
6. Välj namnet på arbetare som utförde utvärderingsregistreringen i fältet **arbetare**.
7. I fältet **rader** visas antalet utvärderingsrader som har ställts in för villkorsutvärderingen.
8. Välj en mall för villkorsutvärderingen i fältet **mall**. Namnet på mallen infogas automatiskt i fältet **namn** och de relaterade registreringsraderna infogas på snabbfliken **villkorsbedömningsrader**.
9. Du kan infoga anteckningar som rör den valda villkorsutvärderingen på snabbfliken **anteckningar**.
10. För varje villkorsutvärderingsrad infogar du mätdata i fältet **värde**.
11. Du kan infoga en kommentar som relaterar till den valda registreringsraden på snabbfliken **villkorsutvärderingsrader** > fältet **kommentarer**. Om du lägger till en kommentar på en rad markeras kryssrutan **Kommentar** automatiskt.

När du har gjort en registrering av villkorsutvärdering på en tillgång kan du skriva ut en villkorsutvärderingsrapport.

>[!NOTE]
>Du kan också registrera villkorsutvärdering på en arbetsorder (knappen **tillgångshantering** > **allmänt** > **arbetsorder** > **alla arbetsorder** > **villkorsutvärdering**.)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]