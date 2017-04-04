---
title: "Hjälp, översikt"
description: "Den här artikeln innehåller en översikt över komponenterna i hjälpsystemet för Microsoft Dynamics 365 for Operations. Det innehåller beskrivningar av hur du kan skapa anpassad dokumentation och utbildning för din organisation."
author: margoc
manager: AnnBe
ms.date: 2017-04-04
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
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 240060606c8a2955c3f0a0d47fb25b0cde64c187
ms.lasthandoff: 03/31/2017


---

# <a name="help-overview"></a>Hjälp, översikt

Den här artikeln innehåller en översikt över komponenterna i hjälpsystemet för Microsoft Dynamics 365 for Operations. Det innehåller beskrivningar av hur du kan skapa anpassad dokumentation och utbildning för din organisation. 

Dynamics 365 for Operations inkluderar ett hjälpsystem baserat på två huvudkomponenter:

-   En webbplats med dokumentation
-   Uppgiftsguider

Du hittar både artiklar och aktiviteter stödlinjerna från hjälpfönstret i Dynamics 365 för åtgärder enligt följande skärmbild. [![Hjälpfönstret](./media/help-pane-ops-task-guides-1024x741.png)](./media/help-pane-ops-task-guides.png) i den här artikeln beskrivs hjälpsystemet och förklarar hur du skapar anpassade dokumentation och resurser för din organisation.

## <a name="help-on-docsmicrosoftcom"></a>Hjälp om docs.microsoft.com
Webbplatsen för docs.microsoft.com ([docs.microsoft.com/dynamics365/operations](https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) är den primära källan med Produktinformation om Dynamics 365 för operationer. Webbplatsen innehåller följande funktioner:

-   **Tillgång till det senaste innehållet** – webbplatsen ger oss ett snabbare och mer flexibelt sätt att skapa, distribuera och uppdatera produktdokumentation. Därför garanterar den att du har tillgång till den senaste tekniska informationen.
-    **Innehåll som skrivits av experter** – webbplatsen tillhandahåller en större uppsättning produktdokumentationen som medlemmar både i och utanför Microsoft kan förbättras.
-   ** Tillgång till olika slags innehåll **-webbplatsen kan du snabbt åtkomst olika typer av information om Dynamics 365 för operationer, till exempel Microsoft Office Mix presentationer aktiviteter stödlinjerna, videoklipp och wiki-artiklar.
-    **Innehåll som stöder affärsprocesserna** – webbplatsen innehåller business process – fokuserar innehåll som drar fördel av den Modellerare BPM (Business Process) i Microsoft Dynamics Lifecycle Services (LCS).

Vi har flyttats från vår föregående hjälp-wiki allt innehåll till dokument. Vi är mycket nöjda med vår nya webbplats och hoppas som du för.

### <a name="when-can-we-use-it"></a>När använder vi den?

Du kan läsa innehållet på dokument just nu – är offentlig och fullständigt sökbart utan att behöva logga in. Du kan använda alla dina favoritsökmotorer för att söka efter innehåll. Du kan kommentera artiklar på webbplatsen om du väljer genom att logga in med ett konto för GitHub.


## <a name="task-guides"></a>Uppgiftsguider
En aktivitet guide är en kontrollerad, interaktiv, interaktiv upplevelse som leder dig genom stegen för en aktivitet eller affärsprocess. Du kan öppna en uppgift (play) guide från hjälpfönstret. När du klickar på en aktivitet guide visas visas hjälpfönstret stegvisa instruktioner för uppgiften. Lokaliserade uppgiften guiderna är nu tillgängliga. [![Guide för uppgiften visar](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png) starta interaktiv, interaktiv upplevelse, klicka på **Starta aktivitet guide** längst ner i hjälpfönstret. En svart pekare öppnas och visar åtgärden som du måste utföra. Följ beskrivningarna som anges i gränssnittet och ange data som anvisat. [![Uppgift för steg instruktioner](./media/task-guide-step-1-ops.png)](./media/task-guide-step-1-ops.png)**viktigt:** data som du anger när du spelar upp en aktivitet guide är riktiga. Om du arbetar i en produktionsmiljö anges data i företaget som du för närvarande använder.

### <a name="it-all-begins-with-task-recorder"></a>Allt börjar med uppgiftsregistreraren

Uppgiftsguider skapas genom med uppgiftsregistreraren. När du använder uppgiftsregistreraren registreras alla åtgärder du utför i användargränssnittet för Dynamics 365 for Operations UI (som att klicka på menyer, ändra inställningar eller ange data). Stegen som du registrerar kallas gemensamt för en uppgiftsregistrering Som vi förklarade i det föregående avsnittet, kan uppgiftsregistreringar visas i fönstret Hjälp och spelas som uppgiftsguider. Det finns dock andra sätt att använda uppgiftsregistrering:

-   **Spara uppgiftsregistrering i BPM** – Du kan spara en uppgiftsregistrering på en rad i en hierarki i ett BPM-bibliotek i LCS. När du sparar en uppgiftsregistrering i BPM, genereras och visas ett flödesschema tillsammans med stegen för inspelningen. **Obs!** Om du vill visa en uppgiftsregistrering i hjälpfönstret för Dynamics 365 for Operations och spela upp den som en uppgiftsguide, måste du spara registreringen i ett BPM-bibliotek.
-   **Spara uppgiftsregistrering som Word-dokument** – Genom att spara en uppgiftsregistrering som ett Microsoft Word-dokument kan du enkelt producera utskrivbara utbildningsguider för din organisation.

Mer information om Uppgiftsinspelning finns [Uppgiftsinspelning i Dynamics 365 för](../user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Skapa anpassade uppgiftsregistreringar

Du kan skapa egna uppgiftsregistreringar eller så hämta och anpassa uppgiftsregistreringen som Microsoft tillhandahåller. Därför kan du skapa anpassad hjälp för din organisation som återspeglar din specifika implementering av Dynamics 365 for Operations. Visar en uppgift i Dynamics 365 för operationer hjälpfönstret och spelas upp som en aktivitet måste du spara inspelningen i ett bibliotek LCS BPM. Om du är en partner samt främja ett bibliotek till ett företag och inkludera den i en lösning kan vara det tillgänglig för dina kunder. Utförliga instruktioner finns i [skapa dokumentation eller teknisk utbildning med uppgiften inspelningar](../user-interface/task-recorder.md).

## <a name="in-product-help"></a>Produkthjälp
Hjälpinnehållet i Dynamics 365 för operationer antingen klicka på den **hjälp** (**?**) ikonen och välj hjälp eller trycker på Ctrl + Skift +. I båda fall öppnas fönstret Hjälp. Du hittar i Hjälp-fönstret artiklar eller aktiviteter stödlinjerna. [![](./media/help-pane-wiki-1024x684.png)](./media/help-pane-wiki.png)

### <a name="accessing-articles-from-the-help-pane"></a>Komma åt artiklar på hjälpfönstret

Du kommer åt artiklar som gäller Dynamics 365 operationer klient från Hjälp-fönstret. När du först öppnar hjälpfönstret och klicka på den **Wiki** fliken visas artiklarna som gäller för den sida som du använder på Dynamics 365 för operationer. Om inga artiklar finns kan du ange nyckelord om du vill begränsa sökningen. När du klickar på en artikel i hjälpfönstret en ny flik öppnas i webbläsaren och visar artikeln. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Komma åt aktiviteter stödlinjerna på hjälpfönstret

Innan du når guiderna uppgift från hjälpfönstret systemadministratör måste den **systemparametrar** sidan i Dynamics 365 för operationer och konfigurera vissa inställningar. **Anteckningar:**

-   Du måste vara inloggad på ett konto med samma innehavare som den där Dynamics 365 for Operations används, om du vill konfigurera hjälpavsnittet.
-   Det går inte att ansluta till ett LCS-bibliotek från en instans av Dynamics 365 for Operations som körs på en virtuell hårddisk (VHD).

[![Systemparameterformuläret med hjälp inställningar](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) på de **systemparametrar** sidan, gör du följande:

1.  **Viktigt: **Första gången du öppnar hjälpfliken måste du ansluta till Lifecycle Services. Kom ihåg att klicka på länken mitt i formuläret vänta tills anslutningen, stänga dialogrutan och klicka på OK för att komma åt formuläret Parametrar. [![Når LCS](./media/connect-to-lcs-crop-1024x365.png)](./media/connect-to-lcs-crop.png)
2.  Välj Lifecycle Services-projektet att ansluta till.
3.  Välj BPM-biblioteken (inom det valda projektet) att hämta uppgiftsregistreringar från.
4.  Välj BPM-bibliotekens visningsordning. Detta bestämmer i vilken ordning som uppgiftsregistreringar från biblioteken visas i fönstret Hjälp.

När en systemadministratör har slutfört de här stegen kan du öppna Hjälp-fönstret och klicka på fliken **Uppgiftsguider**. Nu visas aktiviteter stödlinjerna som gäller för den sida som du använder på Dynamics 365 för operationer. Om det finns inga stödlinjer uppgift ange du nyckelord om du vill begränsa sökningen. Hjälpfönstret visar stegvisa instruktioner och guiden uppgiften kan spelas upp när du klickar på en aktivitet guide i hjälpfönstret. [![Uppgift för läsläge](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png)

### <a name="where-are-the-translated-task-guides"></a>Var är översatta aktiviteter stödlinjerna?

Översätta uppgiften guiderna övergår i bibliotek "Alla språk" i titeln. I Dynamics 365 för åtgärder om du vill se lokaliserad aktivitet guide hjälper Kontrollera att du är ansluten till ett bibliotek med apppropriate. Det språk som utgångspunkt för aktiviteten visas i kontrolleras för varje användare av språkinställningar under **alternativ**&gt;**inställningar**. 
-   Om en aktivitet guide har översatts när du öppnar uppgiften konfigurationsguiden visas all text i aktivitet guide på det valda språket.
-   Om en aktivitet guide inte har har översatts, när du öppnar det, visas bara en del av texten (text kontroller) på det valda språket.

## <a name="additional-resources"></a>Ytterligare resurser
Följande tabell anger webbplatser med Microsoft Dynamics 365 for Operations-innehåll. Våra innehållswebbplatser är ordnade för att stödja kundlivscykeln. Varje fas stöds av en annan uppsättning webbplatser. Platser med en asterisk (\*) kräver att du loggar in med ett konto som är kopplat till en serviceplan bredvid namnet.

| Plats                                                                     | beskrivning                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Docs.microsoft.com](https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) | Värdar eller länkar till all produktdokumentation för Dynamics 365 for Operations.                                                                                                                                                               |
| [Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Tillhandahåller en molnbaserad samarbetsyta som kunder och partners kan använda för att hantera Dynamics 365 for Operations-projekt från förförsäljning till implementering och åtgärder. Den här webbplatsen är användbar för alla implementeringsfaser. |
| [CustomerSource](http://www.customersource.com/)\*                       | Är värd för omfattande utbildningsresurser och är den primära supportwebbplatsen för Dynamics 365 for Operations. Inloggning kan krävas för åtkomst till specifika resurser på webbplatsen.                                                                      |
| [Stöd för blogg](http://aka.ms/AXSupportBlog)                              | Ger tips som har lagts in av Dynamics 365 for Operations-supportteamet.                                                                                                                                                  |
| [MSDN](http://aka.ms/AXMSDN)                                             | Värd för innehåll från tidigare publiceringar skrivna för utvecklare.                                                                                                                                                                       |
| [TechNet](http://aka.ms/TechNet)                                         | Värd för tidigare publiceringar skrivna för IT-ansvariga och programanvändare.                                                                                                                                           |
| [Dynamics-webbgruppen](http://community.dynamics.com/en/)                  | Värd för bloggar, forum och videor.                                                                                                                                                                                                           |
| [Microsoft.com/Dynamics/](http://www.microsoft.com/dynamics/)                 | Information om utvärdering och försäljning.                                                                                                                                                                                                 |



<a name="see-also"></a>Se även
--------

[Hjälpen för Dynamics 365 för operationer (nedladdningsbara faktum ark)](https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Uppgiftsinspelning för operationer i Microsoft Dynamics 365](../user-interface/task-recorder.md)

[Skapa dokumentation eller utbildning med uppgiftsregistreringar](../user-interface/task-recorder.md)

[Ny eller uppdaterad uppgift får (November 2016)](new-task-guides-november-2016.md)<ph id="t1"></ph>[ny eller uppdaterad uppgift får (augusti 2016)](new-updated-task-guides-available-august-2016.md)<ph id="t2"></ph>[ny eller uppdaterad uppgift får (maj 2016)](new-updated-task-guides-available-may-2016.md)<ph id="t3"></ph>[får ny uppgift (februari 2016)](new-task-guides-available-february-2016.md)






