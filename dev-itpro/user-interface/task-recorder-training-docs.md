---
title: Skapa dokumentation eller utbildning med uppgiftsregistreringar
description: "Det här avsnittet beskrivs vilka Uppgiftsinspelning och aktiviteter stödlinjerna är, hur du skapar aktiviteten inspelningar och hur du anpassar Microsoft uppgiften leder och inkludera dem i din hjälp."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: 38bce4a843f0db575c8d1ba08b7dc2ece8366663
ms.lasthandoff: 03/31/2017


---

# <a name="create-documentation-or-training-using-task-recordings"></a>Skapa dokumentation eller utbildning med uppgiftsregistreringar
Det här avsnittet beskrivs vilka Uppgiftsinspelning och aktiviteter stödlinjerna är, hur du skapar aktiviteten inspelningar och hur du anpassar Microsoft uppgiften leder och inkludera dem i din hjälp.

<a name="learn-about-task-recorder"></a>Läs om uppgiftsregistrering
-------------------------

Uppgiftsinspelning är en Microsoft Dynamics 365 för åtgärder som du kan använda för att spela in åtgärder som du kan utföra i produktens användargränssnitt (UI). När du använder uppgiftsregistrering spelas alla händelser som du utför i UI, som utförs mot servern, inklusive lägga till värden, ändra inställningar, ta bort data, in. Stegen som du registrerar kallas gemensamt för en *uppgiftsregistrering* Uppgiftsregistrering kan användas på flera sätt:

-   **Uppgiftsregistrering kan spelas upp som uppgiftsguider.** Uppgiften stödlinjer är en integrerad del av Dynamics 365 på operationer som hjälper dig. En aktivitet guide är en kontrollerad, interaktiv, interaktiv upplevelse steg i en affärsprocess. Användaren uppmanas avsluta varje steg med en prompt ("eller bubbla") som animerar i UI och pekar på UI-elementet som användaren ska interagera med. "Bubblan" innehåller även information om ska kunna arbeta med element, till exempel "Klicka här" eller "I det här fältet anger du ett värde". En aktivitet guide körs mot användarens aktuella datauppsättningen och informationen som anges sparas i användarens miljö.
-   **Uppgiften inspelningar kan visas som procedurmässig stegen i hjälpfönstret.** Du kan använda åtgärdsfönstret Hjälp att söka efter och visa uppgift inspelningar. Du kan använda hjälpfönstret genom att klicka på den **?** Ikonen i det övre navigeringsfältet eller du kan använda tangentkombinationen **Ctrl + Skift +?**. Du kan också läsa steg i en uppgift i hjälpfönstret eller du kan välja att spela upp inspelningen som utgångspunkt för uppgiften så att guiden leder dig genom Användargränssnittet.
-   **Uppgiftsregistreringar kan sparas i BPM.** Du kan spara dina uppgiftsregistreringar på en rad i en hierarki i ett Business Process Modeler-bibliotek (BPM) i Lifecycle Services (LCS). En lista över steg och en affärsflödesplan genereras från inspelningen. Uppgiften inspelningar som har sparats i ett bibliotek i BPM kan visas i Dynamics 365 for Operations form.
-   **Uppgiftsregistreringar kan sparas som Word-dokument.** På så sätt kan du enkelt producera utskrivbara utbildningsguider.

Du kan skapa uppgift inspelningar, spela upp aktiviteten inspelningar från Microsoft eller ändra inspelningar Microsoft aktiviteten så att den avspeglar din konfiguration. Mer information om Uppgiftsinspelning finns [Uppgiftsinspelning i Dynamics 365 för](task-recorder.md).

## <a name="plan-your-task-recording"></a>Planera uppgiftsregistrering
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
-   För varje steg i en uppgiftsregistrering kan du skapa kommentarer. Under uppspelning av en uppgiftsguide visas kommentarer i "bubblan" som anteckningar över eller under texten för steget. Anteckningar visas som infogade text i steg visas som text i hjälpfönstret. Som med beskrivningen är det en bra idé att skriva och spara dina kommentarer i ett separat dokument. När du registrerar uppgiften, klipp och klistra in kommentarerna in från det dokumentet.

**Förstå de olika kommentarstyperna** Alla kommentarer är valfria. Lägga bara till dem när de ger användbar information till användaren.

-   **Rubrik**: en anteckning titel visas innan texten steg som registrerade uppgift automatiskt genererar. I guiden uppgiften visas titel anteckning ovanför den automatiskt genererade texten. Använd den här typen av kommentar för att förklara varför användaren utför steget eller för att ange ytterligare kontext.

Detta är redigeringsfönstret som visas när du lägger till en kommentar när du skapar registreringen. Ange en rubrik kommentar i rutan **Title**. 

[![screen1](./media/screen1.png)](./media/screen1.png) 

Detta är vad rubrikkommentarer ser ut som i "bubblan” i uppgiftsguiden. 

[![screen2](./media/screen2.png)](./media/screen2.png)

-   **Anteckningar:** En anteckningskommentar visas efter stegtexten som uppgiftsregistrering genererar automatiskt. I uppgiftsguiden är den bara synlig om användaren klickar på länken **Visa mer** i uppgiftsguidens bubbla. Använd den här kommentarstypen för att beskriva allt som användaren måste veta för att slutföra steget.

Detta är redigeringsfönstret som visas när du lägger till en kommentar när du skapar registreringen. Ange en anteckningskommentar i rutan **Notes **. 

[![screen3](./media/screen3.png)](./media/screen3.png) 

Detta är anteckningar anteckning ser ut i "bubblan" i guiden för uppgiften.

[![screen4](./media/screen4.png)](./media/screen4.png)

-   **Steg Info**: de här anteckningarna skapats genom att högerklicka på en kontroll eller någonstans i ett formulär &lt;**Uppgiftsinspelning**&lt; ** steget Lägg till information. ** Info steg visas som ett numrerade steg vid tidpunkt du infogar, även om ingenting har rapporterats i Användargränssnittet. Du kan lägga till ett informationssteg på formulärnivå eller ett informationssteg associerat med en kontroll. När ett informationssteg tillhör ett formulär visas uppgiftsguidens "bubbla" någonstans i formuläret utan pekare när uppgiftsguiden spelas upp. När ett steg info är associerad med en kontroll, pekar aktivitet guide "bubbeldiagram" på kontrollen när guiden uppgift spelas. I hjälpfönstret visas en info steg anteckningen som ett numrerade steg med texten du angett. Göra information för att förbereda du i nästa steg beskriver steg som måste utföras utanför Dynamics 365 för operationer eller referera till andra inspelningar (men du inte kan skapa hyperinks i anteckningar.).

**Avgör hur långa registreringen ska vara**

-   Användaren kommer antingen att läsa eller spela upp registreringen från början till slut, så kombinera inte steg eller uppgifter som görs bättre separat.
-   Försök inte att registrera ett långt scenario som omfattar flera underprocesser. Till exempel är Arbeta i butikens kundtjänst för allmänt. Bryt det upp till kortare uppgifter som till exempel Ta emot returer och Lägg till på presentkort.
-   Om en uppgift kan utföras som en del av flera olika affärsprocesser, skapa en separat registrering för den och du kan referera till den i de andra registreringarna.
-   Om processen gäller flera uppgifter som personen troligen gör samtidigt, kan du behålla uppgifterna i en registrering, till exempel Ställ in och tilldela funktionsprofiler.
-   Om det är något som görs en gång (till exempel konfiguration) och sedan en annan uppgift som de kan göra omedelbart efteråt men flera gånger och fristående, bryt upp dem till två uppgiftsregistreringar.

**Bestämmer var i Användargränssnittet att starta en inspelning** sidan som visas i när du börjar spela in en uppgift inspelning påverkar vilka sidor guiden uppgift visas för. Exempelvis måste kan din uppgift inspelningen i listan i hjälpfönstret när användaren klickar på Hjälp på sidan redovisningen parametrar du starta inspelningen på sidan parametrar för redovisningen. **Spara registreringar som .axtr-filer** När du har skapat eller redigerat en uppgiftsregistrering får du flera alternativ för att hämta eller spara registreringen. Du kan hämta filen som en uppgiftsregistreringspaket (.axtr), hämta den som en rå registreringsfil (.xml), hämta den som ett Word-dokument eller spara filen i ett LCS-bibliotek. Det är en bra idé att alltid uppgiftsregistreringar som en uppgiftsregistreringspaketfil (.axtr). Detta gör det lättare att underhålla filen enklare om procedurer eller kommentarer måste ändras senare. Om du vill hämta filen som ett Word-dokument, spara den även uppgiftsregistreringspaketfil.

## <a name="create-your-task-recording"></a>Skapa en uppgiftsregistrering
Detaljerad hanteringspaketen Se [hur du skapar en uppgift inspelning](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>Kopiera och anpassa Microsofts uppgiftsregistreringar
Du kan hämta och redigera uppgift Microsofts inspelningar för att kunna använda dem för hjälp-dokumentationen eller utbildningsmaterial. Hämta en Microsoft uppgiftsregistrering genom att följa dessa steg:

1.  I Dynamics 365 för operationer, öppna Uppgiftsinspelaren. Uppgiftsregistrering finns på menyn **Inställningar**.
2.  Klicka på **Underhåll en registrering** i fönstret Uppgiftsregistrering.
3.  Under **Var är registreringen?**, klicka på **Den finns i ett LCS-bibliotek**.
4.  Klicka på **Välj LCS-biblioteket**.
5.  Välj Microsoft global library.
6.  Välj biblioteksnoden för affärsprocesser i trädet som uppgiftsregistreringen är kopplad till.
7.  Klicka på **OK**.
8.  Klicka på **Start**.
9.  Nu utför inspelningen, ändra alla steg åt spelar in det igen. **Observera**: Om du bara behöver ändra texten i en inspelning du öppnar inspelningen i **redigera anteckningar om en inspelning** läge och spara den.
10. När registreringen har spelat till slutet, klicka på **Stoppa** i uppgiftsregistreringsfältet överst på skärmen.
11. Välj hur du vill spara uppgiftsregistreringen.

## <a name="include-your-task-recordings-in-the-help-pane"></a>Inkludera uppgift inspelningar i hjälpfönstret
Om du vill visa aktiviteter inspelningar i hjälpfönstret så att de kan spelas upp som aktiviteter stödlinjerna eller visas som text, du spara uppgiften inspelningar i BPM bibliotek och uppdatera din hjälp systemparametrar till biblioteket BPM. Mer information finns i [ansluta hjälpsystemet.](../get-started/help-connect.md)

<a name="see-also"></a>Se även
--------

[Hjälpen för Dynamics 365](..\get-started\help-overview.md)

[Ansluta hjälp](..\get-started\help-connect.md)

[Uppgiftsinspelning i Dynamics 365 för operationer](task-recorder.md)

[Nyligen tillagda funktioner som registrerade uppgiften](\core\get-started\recently-added-editing-features-in-task-recorder)

[Skapa nya bibliotek utbildning för Dynamics AX inom Lifecycle Services med Uppgiftsregistering (extern länk)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)

[Skapa Rich hjälpavsnitt med Uppgiftsinspelaren (extern länk)](https://mbspartner.microsoft.com/AX/Videos/970)


