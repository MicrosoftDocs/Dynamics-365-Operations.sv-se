---
title: "Personaladministrering (översikt)"
description: "Detta avsnitt diskuterar hur du kan använda tjänsten för personaladministrering (Workforce management, eller WFM) för att dra nytta av välbekanta kassaklienter, moderna kassasystem och kassasystem via moln, så att butikschefer lättare kan hantera sin personal."
author: shalabhjainmsft
manager: AnnBe
ms.date: 7/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-07-30
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d67ad79c068651f32ce7dc776bc460698557bc29
ms.openlocfilehash: f747dce6b9595de50297cb5af7db523d5f26a844
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="workforce-management-overview"></a>Personaladministrering (översikt)

[!include[banner](includes/banner.md)]
    
Tjänsten för personaladministrering (WFM) utnyttjar välbekanta kassaklienter, moderna kassasystem och kassasystem via moln, så att butikschefer lättare kan hantera sin personal. WFM-tjänsten använder ramverket för tillägg för att hämta relevanta paket till kassasystemet. Dessa paket hämtas när kassasystemet stängs ner och öppnas på nytt. Kassa-appen måste därför stängas ner och öppna på nytt när Microsoft släpper nya funktioner för WFM.

Genom att använda denna tjänst kan butikschefer enkelt skapa och publicera veckoscheman för sina butiker. Butikspersonalen kan sedan snabbt granska sina och kollegornas scheman. På så sätt kan de få veta vem de kommer att arbeta tillsammans med under sina skift. Butikspersonalen kan också registrera begäran om ledighet, skiftbyten och skifterbjudanden. Alla dessa begäranden utlöser ett fördefinierat arbetsflöde.

Under själva skiftet kan butikspersonalen utnyttja in- och utstämplingsfunktionerna som finns inbyggda i kassaklienterna. Datan skickas sedan till huvudkontoret för lönebearbetning. In- och utstämplingsfunktionen är en befintlig funktion i kassasystemet. Mer information om de inställningar och scenarier som stöds finns i [In- och utstämpling](retail-time-attendance.md).

## <a name="supported-scenarios"></a>Stödda scenarier
I detta avsnitt finns mer information om de scenarier som stöds.

- **Skapa och publicera scheman** – WFM-tjänsten använder de behörigheter i kassasystemet som finns konfigurerade på huvudkontoret för att avgöra huruvida en medarbetare har butikschefsprivilegier. Endast butikschefer kan skapa och publicera scheman genom att använda funktionen för schemaadministrering. Dessa kan snabbt skapa ett schema genom att kopiera och klistra in ett befintligt arbetsskift från en medarbetare till en annan. De kan även skapa ett schema genom att importera schemat från valfri tidigare vecka till aktuell vecka.

    Om ett schema inte publiceras har det statusen "utkast" och ser annorlunda ut än ett publicerat schema. Butikschefer kan publicera ett schema genom att klicka på knappen **Publicera** för valfri vecka. När schemat har varit publicerat i en vecka publiceras eventuella ändringar automatiskt. Exempel på ändringar inkluderar tillägg/radering av arbetsskift eller frånvaro, samt ändringar på arbetsskift eller frånvaro. Butiksmedarbetare kan endast se scheman som publicerats för olika veckor.
    
- **Skapa och godkänna begäranden** – Butiksmedarbetare kan skapa tre lika typer av begäranden:

    - Begäran om frånvaro
    - Begäran om skiftbyte
    - Begäran om skifterbjudande

    Dessa begäranden kan skapas genom att använda schemats begärandefunktion. Varje begäran följer ett definierat arbetsflöde, och medarbetarna kan enkelt se aktuell status för sina begäranden.
    
    Begäranden om frånvaro skickas automatiskt till butikschefen för godkännande. Om det finns mer än en butikschef kan samtliga butikschefer se en inskickad begäran, men endast en chef kan godkänna eller neka den. Frånvarotyperna anges på huvudkontoret genom att använda sidan **Ledighets- och frånvarotyper** i modulen **Återförsäljning**. Efter det att butikschefen har godkänt eller nekat en begäran, flyttas denna till fliken **Historik** för funktionen för schemabegäranden.
    
    Ett skitfbyte eller en skiftbegäran skickas först till den medarbetare som begäran skickades till. Butikschefen kan granska begäran först efter det att medarbetaren har godkänt den. Om medarbetaren nobbar skiftbytet eller begäran om skifterbjudande, kan chefen därför inte se bytet/erbjudandet. Den medarbetare som skapat begäran kan även annullera den innan chefen godkänner eller nekar den.

- **Visa aktiva butiksmedarbetare i schemaläggningsvyn** – När en medarbetare läggs till i en butik - exempelvis genom att han/hon kopplas till butikens adressbok över medarbetare- blir han/hon tillgänglig att schemaläggas i WFM-tjänsten. Ett återkommnde batch-jobb kallat **Bearbeta medarbetardata för personaladministrering** körs på huvudkontoret. Detta jobb förbereder butiksmedarbetarens kopplingar som skickas till Common Data Service (CDS).

    Samma process används när en medarbetare tas bort från butiken. Den medarbetare som tas bort visas emellertid fortsatt för tidigare, aktuella och framtida veckor om denne har tilldelats ett aktivt arbetsskift eller frånvaro. Såvida sådana arbetsskiften eller sådan frånvaro inte raderas kommer den borttagne medarbetaren därför att visas under dessa veckor.

