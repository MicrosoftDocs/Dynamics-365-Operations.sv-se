---
title: "Hjälpöversikt"
description: "Den här artikeln innehåller en översikt över komponenterna i hjälpsystemet för Microsoft Dynamics 365 for Operations. Det innehåller beskrivningar av hur du kan skapa anpassad dokumentation och utbildning för din organisation."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16381
ms.assetid: 018c148c-9cbd-41e0-8186-d75dbf66288f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6f785ac8b9a8be503bf9122f21716f745b17115b
ms.openlocfilehash: f08434b4c818460009644e77da1b37ba86cc1d54
ms.contentlocale: sv-se
ms.lasthandoff: 04/27/2017


---

# <a name="help-overview"></a>Hjälpöversikt

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller en översikt över komponenterna i hjälpsystemet för Microsoft Dynamics 365 for Operations. Det innehåller beskrivningar av hur du kan skapa anpassad dokumentation och utbildning för din organisation. 

Dynamics 365 for Operations inkluderar ett hjälpsystem baserat på två huvudkomponenter:

-   En dokumentationsplats
-   Uppgiftsguider

Du har tillgång till både artiklar och uppgiftsguider via Hjälp-fönstret i Dynamics 365 for Operations enligt följande skärmdump. [![Help pane](./media/help-pane-ops-task-guides-1024x741.png)](./media/help-pane-ops-task-guides.png) Den här artikeln innehåller en beskrivning av hjälpsystemet och förklarar hur du kan skapa anpassad dokumentation och anpassade utbildningsresurser för din organisation.

## <a name="help-on-docsmicrosoftcom"></a>Hjälp om docs.microsoft.com
Webbplatsen docs.microsoft.com ([docs.microsoft.com/dynamics365/operations](/dynamics365/#pivot=solutions&panel=solutions_operations) är den primära källan för produktinformation om Dynamics 365 for Operations. Webbplatsen erbjuder följande funktioner:

-   **Åtkomst till det senaste innehållet**– Webbplatsen ger oss ett snabbare och mer flexibelt sätt att skapa, leverera och uppdatera produktdokumentation. Därför garanterar den att du har tillgång till den senaste tekniska informationen.
-   **Innehåll skrivet av experter**– Webbplatsen ger en större mängd produktdokumentation som kan förbättras av community-medlemmar både inom och utanför Microsoft.
-   **Åtkomst till andra typer av innehåll** – Webbplatsen ger dig snabb åtkomst till olika typer av innehåll om Dynamics 365 for Operations, till exempel Microsoft Office Mix-presentationer, uppgiftsguider, videor och avsnitt.
-   **Innehåll som stöder dina affärsprocesser**– Webbplatsen innehåller affärsprocessfokuserat innehåll som använder affärsprocessmodelleraren (Business Process Modeler, BPM) i Microsoft Dynamics Lifecycle Services (LCS).

Vi har flyttat allt innehåll från vår föregående hjälp-wiki till dokument. Vi är mycket stolta över vår nya webbplats och hoppas att även du gillar den.

### <a name="when-can-we-use-it"></a>När använder vi den?

Du kan läsa innehåll i dokument nu direkt -- det är helt offentligt och sökbart utan att kräva inloggning. Du kan använda alla dina favoritsökmotorer för att söka efter innehåll. Om du vill kan du kommentera artiklar på webbplatsen genom att logga in.


## <a name="task-guides"></a>Uppgiftsguider
En uppgiftsguide är en kontrollerad, guidad, interaktiv upplevelse som leder dig genom stegen för en uppgift eller en affärsprocess. Du kan öppna (spela upp) en uppgiftsguide via fönstret Hjälp. När du först klickar på en uppgiftsguide visar fönstret Hjälp steg för steg-instruktionerna för uppgiften. Nu finns det lokaliserade uppgiftsguider. [![Läsvy för uppgiftsguide](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png) Starta den guidade, interaktiva upplevelsen genom att klicka på **Starta uppgiftsguide** längst ned i fönstret Hjälp. En svart pekare öppnas och visar åtgärden som du måste utföra. Följ beskrivningarna som anges i gränssnittet och ange data som anvisat. [![Steginstruktion för uppgiftsguide](./media/task-guide-step-1-ops.png)](./media/task-guide-step-1-ops.png) **Viktigt:** De data som du matar in när du spelar upp en uppgiftsguide är verkliga. Om du arbetar i en produktionsmiljö anges data i företaget som du för närvarande använder.

### <a name="it-all-begins-with-task-recorder"></a>Allt börjar med uppgiftsregistreraren

Uppgiftsguider skapas genom med uppgiftsregistreraren. När du använder uppgiftsregistreraren registreras alla åtgärder du utför i användargränssnittet för Dynamics 365 for Operations UI (som att klicka på menyer, ändra inställningar eller ange data). Stegen som du registrerar kallas gemensamt för en uppgiftsregistrering Som vi förklarade i det föregående avsnittet, kan uppgiftsregistreringar visas i fönstret Hjälp och spelas som uppgiftsguider. Det finns dock andra sätt att använda uppgiftsregistrering:

-   **Spara uppgiftsregistrering i BPM** – Du kan spara en uppgiftsregistrering på en rad i en hierarki i ett BPM-bibliotek i LCS. När du sparar en uppgiftsregistrering i BPM, genereras och visas ett flödesschema tillsammans med stegen för inspelningen. **Obs!** Om du vill visa en uppgiftsregistrering i hjälpfönstret för Dynamics 365 for Operations och spela upp den som en uppgiftsguide, måste du spara registreringen i ett BPM-bibliotek.
-   **Spara uppgiftsregistrering som Word-dokument** – Genom att spara en uppgiftsregistrering som ett Microsoft Word-dokument kan du enkelt producera utskrivbara utbildningsguider för din organisation.

För mer information om uppgiftsinspelaren, se [Uppgiftsinspelaren i Dynamics 365 for Operations](../user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Skapa anpassade uppgiftsregistreringar

Du kan skapa egna uppgiftsregistreringar eller så hämta och anpassa uppgiftsregistreringen som Microsoft tillhandahåller. Därför kan du skapa anpassad hjälp för din organisation som återspeglar din specifika implementering av Dynamics 365 for Operations. Om du vill visa en uppgiftsregistrering i hjälpfönstret för Dynamics 365 for Operations och spela upp den som en uppgiftsguide, måste du spara registreringen i ett BPM-bibliotek i LCS. Om du är partner och befordrar ett bibliotek till ett företagsbibliotek och inkluderar det i en lösning, blir det tillgängligt även för dina kunder. Fullständiga instruktioner finns i [Använda uppgiftsregistreringar för att skapa dokumentation eller utbildning](../user-interface/task-recorder.md).

## <a name="in-product-help"></a>Produkthjälp
För att nå hjälpavsnittet i Dynamics 365 for Operations , klicka antingen på ikonen **Hjälp** (**?**) och välj sedan Hjälp, eller trycks på Ctrl+Shift+?. I båda fall öppnas fönstret Hjälp. I fönstret Hjälp kan du öppna artiklar eller uppgiftsguider. [![Hjälpfönster](./media/help-pane-wiki-1024x684.png)](./media/help-pane-wiki.png)

### <a name="accessing-articles-from-the-help-pane"></a>Öppna artiklar via hjälpfönstret

Via fönstret Hjälp kan du öppna artiklar som gäller för Dynamics 365 for Operations-klienten. När du först öppnar hjälpfönstret och klickar på fliken **Wiki** ser du de artiklar som gäller för den sida du för närvarande använder i Dynamics 365 for Operations. Om inga artiklar hittas kan du ange nyckelord för att begränsa sökningen. När du klickar på en artikel i fönstret Hjälp öppnas en ny flik i webbläsaren som visar artikeln. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Öppna uppgiftsguider via hjälpfönstret

Innan du kan få åtkomst till uppgiftsguiderna via hjälpfönstret måste en systemadministratör öppna sidan **Systemparametrar** i Dynamics 365 for Operations och konfigurera vissa inställningar. **Anteckningar:**

-   Du måste vara inloggad på ett konto med samma innehavare som den där Dynamics 365 for Operations används, om du vill konfigurera hjälpavsnittet.
-   Det går inte att ansluta till ett LCS-bibliotek från en instans av Dynamics 365 for Operations som körs på en virtuell hårddisk (VHD).

[![Formulär för systemparametrar med hjälpinställningar](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Gå till sidan **Systemparametrar** och följ dessa steg:

1.  **Viktigt:**Första gången du öppnar hjälpfliken måste du ansluta till Lifecycle Services. Se till att klicka på länken i mitten av formuläret, vänta på anslutningen, stänga dialogrutan och klicka sedan på OK för att nå parameterformuläret.[![Anslut till LCS](./media/connect-to-lcs-crop-1024x365.png)](./media/connect-to-lcs-crop.png)
2.  Välj Lifecycle Services-projektet att ansluta till.
3.  Välj BPM-biblioteken (inom det valda projektet) att hämta uppgiftsregistreringar från.
4.  Välj BPM-bibliotekens visningsordning. Detta bestämmer i vilken ordning som uppgiftsregistreringar från biblioteken visas i fönstret Hjälp.

När en systemadministratör har slutfört de här stegen kan du öppna Hjälp-fönstret och klicka på fliken **Uppgiftsguider**. Du ser nu uppgiftsguiderna som gäller för den sida du för närvarande befinner dig på i Dynamics 365 for Operations. Om inga uppgiftsguider hittas kan du ange nyckelord för att begränsa sökningen. Efter att du har klickat på en uppgiftsguide i Hjälp-fönstret visas steg-för-steg-instruktioner och du kan spela upp uppgiftsguiden. [![Läsningsvy för uppgiftsguide](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png)

### <a name="where-are-the-translated-task-guides"></a>Var finns de översatta uppgiftsguiderna?

Översatta uppgiftsguider publiceras i bibliotek med "Alla språk" i rubriken. Om du vill se hjälpen för den lokaliserade uppgiftsguiden i Dynamics 365 for Operations, se till att du då är ansluten till ett lämpligt bibliotek. Språket i uppgiftsguiden styrs av varje användare via Språkinställningar under **Alternativ** &gt; **Inställningar**. 
-   Om en uppgiftsguide har översatts visas all text i guiden på det valda språket när du öppnar den.
-   Om en uppgiftsguide ännu inte har översatts, visas enbart en del text i guiden (text för kontroller) på det valda språket när du öppnar den.

## <a name="additional-resources"></a>Ytterligare resurser
Följande tabell anger webbplatser med Microsoft Dynamics 365 for Operations-innehåll. Våra innehållswebbplatser är ordnade för att stödja kundlivscykeln. Varje fas stöds av en annan uppsättning webbplatser. Webbplatser som har en asterisk (\*) bredvid namnet kräver att du loggar in med ett konto som är kopplat till ett tjänsteavtal.

| Plats                                                                     | beskrivning                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Docs.microsoft.com](/dynamics365/#pivot=solutions&panel=solutions_operations) | Värdar eller länkar till all produktdokumentation för Dynamics 365 for Operations.                                                                                                                                                               |
| [Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Tillhandahåller en molnbaserad samarbetsyta som kunder och partners kan använda för att hantera Dynamics 365 for Operations-projekt från förförsäljning till implementering och åtgärder. Den här webbplatsen är användbar för alla implementeringsfaser. |
| [CustomerSource](http://www.customersource.com/)\*                       | Är värd för omfattande utbildningsresurser och är den primära supportwebbplatsen för Dynamics 365 for Operations. Inloggning kan krävas för åtkomst till specifika resurser på webbplatsen.                                                                      |
| [Supportblogg](http://aka.ms/AXSupportBlog)                              | Ger tips som har lagts in av Dynamics 365 for Operations-supportteamet.                                                                                                                                                  |
| [MSDN](http://aka.ms/AXMSDN)                                             | Värd för innehåll från tidigare publiceringar skrivna för utvecklare.                                                                                                                                                                       |
| [TechNet](http://aka.ms/TechNet)                                         | Värd för tidigare publiceringar skrivna för IT-ansvariga och programanvändare.                                                                                                                                           |
| [Dynamics Community](http://community.dynamics.com/)                  | Värd för bloggar, forum och videor.                                                                                                                                                                                                           |
| [Microsoft.com/Dynamics/](http://www.microsoft.com/dynamics/)                 | Information om utvärdering och försäljning.                                                                                                                                                                                                 |



<a name="see-also"></a>Se även
--------

[Hjälpsystem för Dynamics 365 for Operations (hämtningsbart faktablad)](https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Uppgiftsregistrerare i Microsoft Dynamics 365 for Operations](../user-interface/task-recorder.md)

[Skapa dokumentation eller utbildning med uppgiftsregistreringar](../user-interface/task-recorder.md)

[Nya eller uppdaterade uppgiftsguider (november 2016)](new-task-guides-november-2016.md)
[Nya eller uppdaterade uppgiftsguider (augusti 2016)](new-updated-task-guides-available-august-2016.md)
[Nya eller uppdaterade uppgiftsguider (maj 2016)](new-updated-task-guides-available-may-2016.md)
[Nya uppgiftsguider (februari 2016)](new-task-guides-available-february-2016.md)








