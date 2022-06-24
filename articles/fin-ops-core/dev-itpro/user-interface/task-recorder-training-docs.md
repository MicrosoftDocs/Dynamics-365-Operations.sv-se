---
title: Skapa dokumentation eller utbildning med uppgiftsinspelning
description: Den här artikeln förklarar vad uppgiftsregistrering och uppgiftsguider är, hur du skapar inspelningar och hur du anpassar Microsoft uppgiftsguider och inkluderar dem i din Hjälp.
author: josaw1
ms.date: 03/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b556003edf2fe186f6b095e538f142fcf5a0bba5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891826"
---
# <a name="create-documentation-or-training-with-task-recorder"></a>Skapa dokumentation eller utbildning med uppgiftsinspelning

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Den här artikeln förklarar vad uppgiftsregistrering och uppgiftsguider är, hur du skapar uppgiftsinspelningar och hur du anpassar Microsoft uppgiftsguider och inkluderar dem i din Hjälp.

> [!IMPORTANT]
> Du kan spela in egna uppgiftsguider för Dynamics 365 Human Resources, men du kan inte spara dem i ett bibliotek för Affärsprocessmodelleraren (BPM) eller öppna dem direkt från fönstret Hjälp just nu. Du kan spara dem lokalt eller på en nätverksplats och sedan öppna och spela upp dem med Uppgiftsinspelaren. 

## <a name="learn-about-task-recorder"></a>Läs om uppgiftsregistrering

Uppgiftsinspelaren är ett verktyg som du kan använda till att registrera åtgärder som du utför i produktanvändargränssnittet (UI). När du använder uppgiftsinspelning spelas alla händelser som du utför i UI, som utförs mot servern, inklusive lägga till värden, ändra inställningar, ta bort data, in. Stegen som du registrerar kallas gemensamt för en *uppgiftsregistrering* Uppgiftsregistrering kan användas på flera sätt:

-   **Uppgiftsregistrering kan spelas upp som uppgiftsguider.** Uppgiftsguider är en integrerad del av Hjälp-upplevelsen. En uppgiftsguide är en kontrollerad, guidad, interaktiv upplevelse som leder dig genom stegen för en affärsprocess. Användaren uppmanas avsluta varje steg med en prompt ("eller bubbla") som animerar i UI och pekar på UI-elementet som användaren ska interagera med. "Bubblan" innehåller även information om hur du interagerar med element som till exempel "Klicka här" eller "I det här fältet anger du ett värde". En uppgiftsguide körs mot användarens aktuella datauppsättning och informationen som anges sparas i användarens miljö.
-   **Uppgiftsregistreringar kan sparas som Word-dokument.** På så sätt kan du enkelt producera utskrivbara utbildningsguider.

Du kan skapa egna uppgiftsregistreringar, spela upp uppgiftsregistreringar som tillhandahålls av Microsoft eller ändra Microsofts uppgiftsregistrering för att återspegla konfigurationen. För mer information om Uppgiftsinspelare, se [Uppgiftsinspelare](task-recorder.md).

## <a name="plan-your-task-recording"></a>Planera uppgiftsregistrering
Om du skapar en ny uppgiftsregistrering eller baserar din registrering på Microsofts uppgiftsregistrering, tänk på följande information.

-   Planera registreringen som för en video. Gör alla dina beslut i förväg.
-   Gå igenom affärsprocessen en eller två gånger utan att registrera den så att du förstår stegen.
-   När du går igenom processen före registreringen, lägg märke till var du använder kortkommandon eller tangenten **Retur**, så att du kan undvika att använda dem under den verkliga registreringen.
-   Identifiera följande:
    -   Vill du gruppera steg till underuppgifter? Underuppgifter avskiljer avsnitt i en process. Om du till exempel du skapar en registrering för "Skapa och släppa en produkt", vill du kanske gruppera stegen som behövs för att skapa en produkt och sedan gruppera stegen som behövs för att släppa produkten. Underuppgifter gör också längre processer enklare att läsa.
    -   Vill du lägga till kommentarer och i så fall var? Mer information finns i Förstå de olika kommentarstyperna nedan.
    -   Vilka värden vill du lägga till i de olika fälten när du slutför stegen för affärsprocessen? Det är en bra idé att veta vad du ska välja eller ange när du går vidare så att du inte går bakåt eller korrigerar misstag när du registrerar.

**Skriv beskrivning och kommentarer i förväg**

-   I början av varje uppgiftsregistrering finns det ett beskrivningsfält som tillåter att du ger en introduktion till registreringen. Det är en bra idé att skriva och spara beskrivningen i förväg i ett separat dokument så att du kan kopiera och klistra in det i uppgiftsregistreringen när du registrerar. På så vis lägger du tid på att förbättra texten när du inte registrerar. När du klipper och klistrar in texten går inspelningsprocessen snabbare och lättare.
-   För varje steg i en uppgiftsregistrering kan du skapa kommentarer. Under uppspelning av en uppgiftsguide visas kommentarer i "bubblan" som anteckningar över eller under texten för steget. När visad som text i hjälpfönstret, visas kommentarers som text infogad i steget. Som med beskrivningen är det en bra idé att skriva och spara dina kommentarer i ett separat dokument. När du registrerar uppgiften, klipp och klistra in kommentarerna in från det dokumentet.

**Förstå de olika kommentarstyperna** Alla kommentarer är valfria. Lägga bara till dem när de ger användbar information till användaren.

-   **Rubrik**: En rubrikkommentarer visas innan stegtexten som uppgiftsregistrering skapar automatiskt. I uppgiftsguiden visas rubrikkommentaren ovanför den automatiskt skapade texten. Använd den här typen av kommentar för att förklara varför användaren utför steget eller för att ange ytterligare kontext.

Detta är redigeringsfönstret som visas när du lägger till en kommentar när du skapar registreringen. Ange en rubrik kommentar i rutan **Rubrik**. 

[![Redigeringsfönster med rubrikanteckning.](./media/screen1.png)](./media/screen1.png) 

Detta är vad rubrikkommentarer ser ut som i "bubblan” i uppgiftsguiden. 

[![Rubrikanteckningens utseende i uppgiftsguiden.](./media/screen2.png)](./media/screen2.png)

-   **Anteckningar:** En anteckningskommentar visas efter stegtexten som uppgiftsregistrering skapar automatiskt. I uppgiftsguiden är den bara synlig om användaren klickar på länken **Visa mer** i uppgiftsguidens bubbla. Använd den här kommentarstypen för att beskriva allt som användaren måste veta för att slutföra steget.

Detta är redigeringsfönstret som visas när du lägger till en kommentar när du skapar registreringen. Ange en anteckningskommentar i rutan **Kommentarer**. 

[![Redigeringsfönster med anteckning i anteckningsrutan.](./media/screen3.png)](./media/screen3.png) 

Detta är vad anteckningskommentar ser ut som i "bubblan” i uppgiftsguiden.

[![Anteckningskommentarens utseende i uppgiftsguiden.](./media/screen4.png)](./media/screen4.png)

-   **Informationssteg**: Dessa anteckningar skapas genom att högerklicka på en kontroll eller någonstans i ett formulär &lt; **Uppgiftsinspelare** &lt; **Lägg till informationssteg.** Informationssteg visas som ett numrerat steg vid den tidpunkt som du infogar det, även om ingen uppgift spelats in i användargränssnittet. Du kan lägga till ett informationssteg på formulärnivå eller ett informationssteg associerat med en kontroll. När ett informationssteg tillhör ett formulär visas uppgiftsguidens "bubbla" någonstans i formuläret utan pekare när uppgiftsguiden spelas upp. När ett informationssteg tillhör en kontroll pekar uppgiftsguidens "bubbla" på kontrollen när uppgiftsguiden spelas upp. I hjälpfönstret visas en informationsstegsanteckning som ett numrerat steg med texten du angett. Använd informationssteg för att förbereda användaren för nästa steg, för att beskriva steg som måste utföras utanför appen eller att hänvisa till andra registreringar (det går dock inte att skapa hyperlänkar i kommentarer).

**Avgör hur långa registreringen ska vara**

-   Användaren kommer antingen att läsa eller spela upp registreringen från början till slut, så kombinera inte steg eller uppgifter som görs bättre separat.
-   Försök inte att registrera ett långt scenario som omfattar flera underprocesser. Till exempel är "Arbeta i butikens kundtjänst" för allmänt. Bryt det upp till kortare uppgifter som till exempel "Acceptera returer" och "Lägg till på presentkort".
-   Om en uppgift kan utföras som en del av flera olika affärsprocesser, skapa en separat registrering för den och du kan referera till den i de andra registreringarna.
-   Om processen gäller flera uppgifter som personen troligen gör samtidigt, kan du behålla uppgifterna i en registrering, till exempel Ställ in och tilldela funktionsprofiler.
-   Om det är något som görs en gång (till exempel konfiguration) och sedan en annan uppgift som de kan göra omedelbart efteråt men flera gånger och fristående, bryt upp dem till två uppgiftsregistreringar.

**Bestäm var i användargränssnittet du startar en inspelning**. Sidan som visas när du börjar spela in en uppgiftsinspelning påverkar vilka sidor uppgiftsguiden visar. Om du exempelvis vill att din uppgiftsinspelning ska visas i listan i hjälpfönstret när användaren klickar på Hjälp på sidan Redovisningsparametrar måste du starta inspelningen på sidan Redovisningsparametrar. **Spara inspelningar som .axtr-filer** När du har skapat eller redigerat en uppgiftsinspelning får du olika alternativ för att hämta eller spara inspelningen. Du kan hämta filen som en uppgiftsregistreringspaket (.axtr), hämta den som en rå registreringsfil (.xml), hämta den som ett Word-dokument eller spara filen i ett LCS-bibliotek. Det är en bra idé att alltid uppgiftsregistreringar som en uppgiftsregistreringspaketfil (.axtr). Detta gör det enklare att underhålla filen om procedurer eller kommentarer måste ändras senare. Om du vill hämta filen som ett Word-dokument ska du även spara den som uppgiftsinspelningspaketfil.

## <a name="create-your-task-recording"></a>Skapa en uppgiftsregistrering
Detaljerad information om stegen finns i [Uppgiftsinspelarresurser](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>Kopiera och anpassa Microsofts uppgiftsregistreringar
Du kan hämta och redigera Microsofts uppgiftsregistreringar för att använda dem för egen hjälpdokumentation eller eget utbildningsmaterial. Hämta en Microsoft uppgiftsregistrering genom att följa dessa steg:

1.  Öppna Uppgiftsinspelaren. Uppgiftsregistrering finns på menyn **Inställningar**.
2.  Klicka på **Underhåll en registrering** i fönstret Uppgiftsregistrering.
3.  Under **Var är registreringen?**, klicka på **Den finns i ett LCS-bibliotek**.
4.  Klicka på **Välj LCS-biblioteket**.
5.  Välj Microsoft globala bibliotek.
6.  Välj biblioteksnoden för affärsprocesser i trädet som uppgiftsregistreringen är kopplad till.
7.  Klicka på **OK**.
8.  Klicka på **Start**.
9.  Nu går du igenom inspelningen och ändrar eventuellt steg under genomgången för att spela in den igen. **Obs!** Om du bara behöver ändra texten i en inspelning kan du öppna inspelningen i läget **Redigera anteckningar om en inspelning** och spara den.
10. När registreringen har spelat till slutet, klicka på **Stoppa** i uppgiftsregistreringsfältet överst på skärmen.
11. Välj hur du vill spara uppgiftsregistreringen.



## <a name="additional-resources"></a>Ytterligare resurser

[Hjälpsystem](../../fin-ops/get-started/help-overview.md)

[Ansluta hjälpsystemet](../../fin-ops/get-started/help-connect.md)

[Uppgiftsinspelare](task-recorder.md)

[Skapa heltäckande hjälpavsnitt med uppgiftsinspelaren (extern länk)](https://mbspartner.microsoft.com/AX/Videos/970)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]