---
title: Skapa dokumentation eller utbildning med uppgiftsregistreringar
description: "Det här avsnittet förklarar vad uppgiftsregistrering och uppgiftsguider är, hur du skapar uppgiftsinspelningar och hur du anpassar Microsoft uppgiftsguider och inkluderar dem i din Hjälp."
author: josaw1
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: ee6d455c44a38d9b3962ca20a5cb28007c19cf1d
ms.openlocfilehash: e71c2638caccb9a31c5254a3cf68c802808960b9
ms.contentlocale: sv-se
ms.lasthandoff: 06/17/2017


---

# Skapa dokumentation eller utbildning med uppgiftsregistreringar
<a id="create-documentation-or-training-using-task-recordings" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Det här avsnittet förklarar vad uppgiftsregistrering och uppgiftsguider är, hur du skapar uppgiftsinspelningar och hur du anpassar Microsoft uppgiftsguider för Unified Operations-produkter och inkluderar dem i din Hjälp.

> [!IMPORTANT]
> Du kan inte skapa anpassade uppgiftsguider för Dynamics 365 for Talent. Hjälpsystemet för Talent ansluts automatiskt till uppgiftsguider för produkten. 

Läs om uppgiftsregistrering
<a id="learn-about-task-recorder" class="xliff"></a>
-------------------------

Uppgiftsinspelaren är ett verktyg som du kan använda till att registrera åtgärder som du utför i produktanvändargränssnittet (UI). När du använder uppgiftsregistrering spelas alla händelser som du utför i UI, som utförs mot servern, inklusive lägga till värden, ändra inställningar, ta bort data, in. Stegen som du registrerar kallas gemensamt för en *uppgiftsregistrering* Uppgiftsregistrering kan användas på flera sätt:

-   **Uppgiftsregistrering kan spelas upp som uppgiftsguider.** Uppgiftsguider är en integrerad del av Hjälp-upplevelsen. En uppgiftsguide är en kontrollerad, guidad, interaktiv upplevelse som leder dig genom stegen för en affärsprocess. Användaren uppmanas avsluta varje steg med en prompt ("eller bubbla") som animerar i UI och pekar på UI-elementet som användaren ska interagera med. "Bubblan" innehåller även information om hur du interagerar med element som till exempel "Klicka här" eller "I det här fältet anger du ett värde". En uppgiftsguide körs mot användarens aktuella datauppsättning och informationen som anges sparas i användarens miljö.
-   **Uppgiftsregistreringar kan visas som processteg i hjälpfönstret.** Du kan använda hjälpfönstret om du vill söka efter och visa uppgiftsregistreringar. Du kan öppna hjälpfönstret genom att klicka på ikonen **?** i det övre navigeringsfältet eller så kan du använda tangentkombinationen **Ctrl + Skift +?**. Läsa stegen för en uppgiftsregistrering i hjälpfönstret eller så kan du välja om du vill spela in som en uppgiftsguide för hjälp i UI.
-   **Uppgiftsregistreringar kan sparas i BPM.** Du kan spara dina uppgiftsregistreringar på en rad i en hierarki i ett Business Process Modeler-bibliotek (BPM) i Lifecycle Services (LCS). En lista över steg och en affärsflödesplan genereras från inspelningen. Uppgiftsinspelningar som sparats i ett BPM-bibliotek kan visas som hjälp.
-   **Uppgiftsregistreringar kan sparas som Word-dokument.** På så sätt kan du enkelt producera utskrivbara utbildningsguider.

Du kan skapa egna uppgiftsregistreringar, spela upp uppgiftsregistreringar som tillhandahålls av Microsoft eller ändra Microsofts uppgiftsregistrering för att återspegla konfigurationen. För mer information om Uppgiftsinspelare, se [Uppgiftsinspelare](task-recorder.md).

## Planera uppgiftsregistrering
<a id="plan-your-task-recording" class="xliff"></a>
Om du skapar en ny uppgiftsregistrering eller baserar din registrering på Microsofts uppgiftsregistrering, tänk på följande information.

-   Planera registreringen som för en video. Gör alla dina beslut i förväg.
-   Gå igenom affärsprocessen en eller två gånger utan att registrera den så att du förstår stegen.
-   När du går igenom processen före registreringen, lägg märke till var du använder kortkommandon eller tangenten **Retur**, så att du kan undvika att använda dem under den verkliga registreringen.
-   Identifiera följande:
    -   Vill du gruppera steg till underuppgifter? Underuppgifter avskiljer avsnitt i en process. Om du till exempel du skapar en registrering för Skapa och släppa en produkt, vill du kanske vill gruppera stegen som behövs för att skapa en produkt och sedan vill gruppera stegen som behövs för att släppa produkten. Underuppgifter gör också längre processer enklare att läsa.
    -   Vill du lägga till kommentarer och i så fall var? Mer information finns i Förstå de olika kommentarstyperna nedan.
    -   Vilka värden vill du lägga till i de olika fälten när du slutför stegen för affärsprocessen? Det är en bra idé att veta vad du ska välja eller ange när du går vidare så att du inte går bakåt eller korrigerar misstag när du registrerar.

**Skriv beskrivning och kommentarer i förväg**

-   I början av varje uppgiftsregistrering finns det ett beskrivningsfält som tillåter att du ger en introduktion till registreringen. Det är en bra idé att skriva och spara beskrivningen i förväg i ett separat dokument så att du kan kopiera och klistra in det i uppgiftsregistreringen när du registrerar. På så vis lägger du tid på att förbättra texten när du inte registrerar. När du klipper och klistrar in texten går inspelningsprocessen snabbare och lättare.
-   För varje steg i en uppgiftsregistrering kan du skapa kommentarer. Under uppspelning av en uppgiftsguide visas kommentarer i "bubblan" som anteckningar över eller under texten för steget. När visad som text i hjälpfönstret, visas kommentarers som text infogad i steget. Som med beskrivningen är det en bra idé att skriva och spara dina kommentarer i ett separat dokument. När du registrerar uppgiften, klipp och klistra in kommentarerna in från det dokumentet.

**Förstå de olika kommentarstyperna** Alla kommentarer är valfria. Lägga bara till dem när de ger användbar information till användaren.

-   **Rubrik**: En rubrikkommentarer visas innan stegtexten som uppgiftsregistrering genererar automatiskt. I uppgiftsguiden visas rubrikkommentaren ovanför den automatiskt genererade texten. Använd den här typen av kommentar för att förklara varför användaren utför steget eller för att ange ytterligare kontext.

Detta är redigeringsfönstret som visas när du lägger till en kommentar när du skapar registreringen. Ange en rubrik kommentar i rutan **Rubrik**. 

[![skärm1](./media/screen1.png)](./media/screen1.png) 

Detta är vad rubrikkommentarer ser ut som i "bubblan” i uppgiftsguiden. 

[![skärm2](./media/screen2.png)](./media/screen2.png)

-   **Anteckningar:** En anteckningskommentar visas efter stegtexten som uppgiftsregistrering genererar automatiskt. I uppgiftsguiden är den bara synlig om användaren klickar på länken **Visa mer** i uppgiftsguidens bubbla. Använd den här kommentarstypen för att beskriva allt som användaren måste veta för att slutföra steget.

Detta är redigeringsfönstret som visas när du lägger till en kommentar när du skapar registreringen. Ange en anteckningskommentar i rutan **Kommentarer**. 

[![skärm3](./media/screen3.png)](./media/screen3.png) 

Detta är vad anteckningskommentar ser ut som i "bubblan” i uppgiftsguiden.

[![skärm4](./media/screen4.png)](./media/screen4.png)

-   **Informationssteg**: Dessa anteckningarna skapats genom att högerklicka på en kontroll eller någonstans i ett formulär &lt; **Uppgiftsregistrering** &lt; **steget Lägg till information. **Informationssteg visas som ett numrerat steg vid den tidpunkt som du infgar det, även om ingen åtgärd rapporterades i användargränssnittet. Du kan lägga till ett informationssteg på formulärnivå eller ett informationssteg associerat med en kontroll. När ett informationssteg tillhör ett formulär visas uppgiftsguidens "bubbla" någonstans i formuläret utan pekare när uppgiftsguiden spelas upp. När ett informationssteg tillhör en kontroll pekar uppgiftsguidens "bubbla" på kontrollen när uppgiftsguiden spelas upp. I hjälpfönstret visas en informationsstegsanteckning som ett numrerat steg med texten du angett. Använd informationssteg för att förbereda användaren för nästa steg, för att beskriva steg som måste utföras utanför Microsoft Dynamics 365 for Finance and Operations, Enterprise edition eller att hänvisa till andra registreringar (det går dock inte att skapa hyperlänkar i kommentarer).

**Avgör hur långa registreringen ska vara**

-   Användaren kommer antingen att läsa eller spela upp registreringen från början till slut, så kombinera inte steg eller uppgifter som görs bättre separat.
-   Försök inte att registrera ett långt scenario som omfattar flera underprocesser. Till exempel är Arbeta i butikens kundtjänst för allmänt. Bryt det upp till kortare uppgifter som till exempel Ta emot returer och Lägg till på presentkort.
-   Om en uppgift kan utföras som en del av flera olika affärsprocesser, skapa en separat registrering för den och du kan referera till den i de andra registreringarna.
-   Om processen gäller flera uppgifter som personen troligen gör samtidigt, kan du behålla uppgifterna i en registrering, till exempel Ställ in och tilldela funktionsprofiler.
-   Om det är något som görs en gång (till exempel konfiguration) och sedan en annan uppgift som de kan göra omedelbart efteråt men flera gånger och fristående, bryt upp dem till två uppgiftsregistreringar.

**Bestäm var i användargränssnittet du startar en inspelning**. Sidan som visas när du börjar spela in en uppgiftsinspelning påverkar vilka sidor uppgiftsguiden visar. Om du exempelvis vill att din uppgiftsinspelning ska visas i listan i hjälpfönstret när användaren klickar på Hjälp på sidan Redovisningsparametrar måste du starta inspelningen på sidan Redovisningsparametrar. **Spara registreringar som .axtr-filer** När du har skapat eller redigerat en uppgiftsregistrering får du flera alternativ för att hämta eller spara registreringen. Du kan hämta filen som en uppgiftsregistreringspaket (.axtr), hämta den som en rå registreringsfil (.xml), hämta den som ett Word-dokument eller spara filen i ett LCS-bibliotek. Det är en bra idé att alltid uppgiftsregistreringar som en uppgiftsregistreringspaketfil (.axtr). Detta gör det lättare att underhålla filen enklare om procedurer eller kommentarer måste ändras senare. Om du vill hämta filen som ett Word-dokument, spara den även uppgiftsregistreringspaketfil.

## Skapa en uppgiftsregistrering
<a id="create-your-task-recording" class="xliff"></a>
Detaljerad information finns i [Skapa en uppgiftsinspelning](task-recorder.md).

## Kopiera och anpassa Microsofts uppgiftsregistreringar
<a id="copy-and-customize-microsofts-task-recordings" class="xliff"></a>
Du kan hämta och redigera Microsofts uppgiftsregistreringar för att använda dem för egen hjälpdokumentation eller eget utbildningsmaterial. Hämta en Microsoft uppgiftsregistrering genom att följa dessa steg:

1.  Öppna Uppgiftsinspelaren. Uppgiftsregistrering finns på menyn **Inställningar**.
2.  Klicka på **Underhåll en registrering** i fönstret Uppgiftsregistrering.
3.  Under **Var är registreringen?**, klicka på **Den finns i ett LCS-bibliotek**.
4.  Klicka på **Välj LCS-biblioteket**.
5.  Välj Microsoft globala bibliotek.
6.  Välj biblioteksnoden för affärsprocesser i trädet som uppgiftsregistreringen är kopplad till.
7.  Klicka på **OK**.
8.  Klicka på **Start**.
9.  Nu går du igenom inspelningen, ändrar eventuellt steg när du går igenom den för att spela in den igen. **Obs!**: Om du bara behöver ändra texten i en inspelning kan du öppna inspelningen i läget **Redigera anteckningar om en inspelning** och spara den.
10. När registreringen har spelat till slutet, klicka på **Stoppa** i uppgiftsregistreringsfältet överst på skärmen.
11. Välj hur du vill spara uppgiftsregistreringen.

## Inkludera dina uppgiftsregistreringar i hjälpfönstret
<a id="include-your-task-recordings-in-the-help-pane" class="xliff"></a>
Om du vill visa dina egna anpassade uppgiftsregistrering i hjälpfönstret så att de kan spelas upp som uppgiftsguider eller visas som text, måste du spara dina uppgiftsregistreringar i ditt eget BPM-bibliotek och sedan uppdatera hjälpsystemparametrarna så att de pekar på ditt BPM bibliotek. Mer information finns i [Ansluta hjälpsystemet](../get-started/help-connect.md).

Se även
<a id="see-also" class="xliff"></a>
--------

[Hjälp – översikt](..\get-started\help-overview.md)

[Anslut hjälp](..\get-started\help-connect.md)

[Uppgiftsinspelare](task-recorder.md)

[Nyligen tillagda uppgiftsregistreringsfunktioner](\core\get-started\recently-added-editing-features-in-task-recorder)

[Skapa heltäckande hjälpavsnitt med uppgiftsinspelaren (extern länk)](https://mbspartner.microsoft.com/AX/Videos/970)

