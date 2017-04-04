---
title: "Anbudsförfrågningar (anbudsförfrågningar)"
description: "Den här artikeln ger en översikt över anbudsförfrågningar (RFQ:er) som organisationer utfärdar när de måste köpa artiklar eller tjänster och vill erhålla konkurrenskraftiga erbjudanden från flera leverantörer. I en anbudsförfrågan ber du leverantörer att ge priser och leveranstiderna för de kvantiteter av artiklar du anger. Du kan också be leverantörerna att ange om det finns några tillfälliga avgifter, till exempel fraktkostnader, eller om leverantören erbjuder rabatter för stora order eller tidig betalning av leverantörsfakturan."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: d70b4ae0a6b177508021ee72481333cf6f265069
ms.lasthandoff: 03/31/2017


---

# <a name="request-for-quotations-rfqs"></a>Anbudsförfrågningar (anbudsförfrågningar)

Den här artikeln ger en översikt över anbudsförfrågningar (RFQ:er) som organisationer utfärdar när de måste köpa artiklar eller tjänster och vill erhålla konkurrenskraftiga erbjudanden från flera leverantörer. I en anbudsförfrågan ber du leverantörer att ge priser och leveranstiderna för de kvantiteter av artiklar du anger. Du kan också be leverantörerna att ange om det finns några tillfälliga avgifter, till exempel fraktkostnader, eller om leverantören erbjuder rabatter för stora order eller tidig betalning av leverantörsfakturan.

Anbudsförfråganprocessen (RFQ) omfattar följande uppgifter:

-   Skapa och skicka en anbudsförfrågan till en eller flera leverantörer
-   Ta emot och registrera svar på anbudsförfrågningar (bud)
-   Överföra accepterade bud till en inköpsorder, ett inköpsavtal eller en inköpsrekvisition

Följande bild ger en översikt över ändringarna i anbudsförfrågansprocessen.  

[![För offertprocessen](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)  

Du kan skapa en anbudsförfrågan från planerade order, från en inköpsrekvisition eller från en manuell post. Anbudsförfrågan som du skapar kallas ett anbudsförfrågansärende och detta är basdokumentet som du använder för att skicka en anbudsförfrågan till varje leverantör. När du förbereder fallet Anbudsförfrågan och lägga till leverantörer klickar du på **skicka** journalen i fallet Anbudsförfrågan och en Anbudsförfrågan skapas för varje leverantör som du har skickat Anbudsförfrågan till. Du kan konfigurera inställningar för åtgärden Skicka om du vill skriva ut en rapport för varje leverantör i ett arkiv eller skicka en rapport till e-postadressen för varje leverantör. Dessutom kan anbudsförfråganjournalen för varje leverantör användas till att generera en rapport som du kan skicka eller skicka om till en leverantör senare. Du kan även konfigurera åtgärden Skicka till att skapa ett svarsblad som leverantören kan fylla i.  

Om du måste ändra en anbudsförfrågan efter att du har skickat den, kan du skicka om anbudsförfrågan till leverantörer när du är klar.  

När du tar emot bud, måste du registrera dem på sidan **Svar på anbudsförfrågan**. Om du väljer alternativet **Kopiera data till svar** kommer data som till exempel kvantitet och data från anbudsförfrågansärende kopieras till svaret. Du kan ändra dessa data så att den avspeglar leverantörens bud.  

Om en andra iteration av ett svar krävs för en viss leverantör, klicka på **Retur **på sidan** Svar på anbudsförfrågan**. Returågärden skapar en ny journal och en rapport som ska skrivas ut, arkiveras och skickas enligt dina inställningar för utskriftshantering.  

Om du har lagt till poängkriterier i ditt anbudsförfrågansärende kommer svaret på anbudsförfrågan ha en poängpanel där du kan ange poängen. De totala poängen visas när du jämför svaren på sidan **Jämför svar **där du också kan jämföra annan svarsinformation som t.ex. radpris, leveransdatum och totalpris.  

När du har bestämt dig för ett bud eller delbud kan du godkänna dem och avvisa resten. Acceptansjournaler, avvisningsjournaler och motsvarande rapporter genereras. De skrivs ut, arkiveras och skickas enligt inställningarna för utskriftshantering. När du accepterar ett erbjudande eller vissa rader i ett erbjudande, antingen ett inköpsavtal inköpsorder eller en inköpsrekvisition uppdateras, beroende på Anbudsförfrågan inköpstyp. Du kan skapa ett handelsavtal som du kan använda senare för någon av svaren, oavsett om du accepterade eller avvisade dem.  

Status för en anbudsförfrågan visas i anbudsförfråganhuvudet och beror på status för anbudsförfrågansraderna. Statusen indikerar i vilken utsträckning du har bearbetat anbudsförfrågan. Varje anbudsförfrågan har två värden för status: lägsta och högsta. Lägsta status är den minst avancerade fasen för vilken rad som helst i en anbudsförfrågan, och den högsta statusen är den mest avancerade fasen för vilken rad som helst i anbudsförfrågan. Om till exempel den minst avancerade fasen i en anbudsförfrågan är för en rad som har skapats, är den lägsta statusen för anbudsförfrågan **Skapad**. Om den mest avancerade fasen i en anbudsförfrågan är för en rad som har skickats till leverantörer är den högsta statusen för anbudsförfrågan **Skickad**. Statusvärdet uppdateras automatiskt under bearbetningen av en anbudsförfrågan.  

Du kan visa lägsta och högsta statusvärde för ett anbudsförfråganhuvud på sidan **Alla anbudsförfrågningar**. Du kan visa lägsta och högsta statusvärde för ett anbudsförfrågansrad på fliken **Rader** på sidan **Anbudsförfrågningar**.  

Här följer ordningen på status för bearbetning av anbudsförfrågningar:

1.  **Created**
2.  **Sent**
3.  **Received**
4.  **Accepterat**/**annullerade**/**avvisades**

Statusvärdet kommer att beskrivas mer utförligt i senare avsnitt i denna artikel.

## <a name="setting-up-rfq-functionality"></a>Ställa in funktionen för anbudsförfrågan
Innan du kan skapa ett anbudsförfrågansärende måste du ställa in information om anbudsförfrågan på sidan **Anskaffnings- och källparametrar**. När du skapar ett anbudsförfrågansärende kan du ange förvalda värden som kopieras till anbudsförfrågan. Du kan ange följande standardvärden:

-   Inköpstypen av nya anbudsförfrågan: **Inköpsorder** eller **Inköpsavtal**
-   Inställningar för utgångsdatum och utgångstid
-   Leveransinformation och betalningsvillkor.
-   Fält som ska vara inkluderade i svaret för anbudsförfrågan

Du kan åsidosätta dessa värden för ett visst anbudsförfråganärende. Du bör också konfigurera ändringsprocessen. Som en del av den här konfigurationen kan du aktivera låsning av fält. När låsning av fält aktiveras, måste en prokurist som vill ändra en anbudsförfrågan, först klicka på **Skapa** i avsnittet **Rättelse** på fältet **Offert**. När Anbudsförfrågan har uppdaterats med ändringar, anskaffning professional måste slutföras genom att klicka på **Slutför**. ** ** The slutföra åtgärden skapar ett e-postmeddelande att meddela leverantörer om ändrade Anbudsförfrågan. Du väljer mallen för e-postmeddelandet som skickas till leverantörer på sidan **Anskaffnings- och källparametrar** . När en mall skapas, kan den innehålla följande utbytestoken:

-   %Orsak till att buden returneras%
-   %Orsak till ändring%
-   %Ändringen har förberetts av%
-   %Företag%

Token för %Orsak till att buden returneras% och %Orsak till ändring% ersätts av text som prokuristen kan ange, när han eller hon avslutar ändringen i guiden **Ändring**. Värdena för token %Ändring förberedd av%, och %Företag% hämtas automatiskt från anbudsförfrågan.  

Om du vill använda orsakskoder för ett svar på en anbudsförfrågan för att ange varför ett bud accepterades eller avvisades, måste du ställa in orsakskoder på sidan **Leverantöranledningar**.  

Du kan konfigurera utseendet på dina utskrivna eller lagrade anbudsförfrågandokument på sidan **Formulärinställningar** i anskaffning och källa.  

När du skapar en anbudsförfrågan för en inköpsorder och lägger till en lagerartikel för anbudsförfrågan, skapas en lagertransaktion som har inleveransstatusen **Offert inleverans**. Endast rader i en anbudsförfrågan som har denna status beaktas när du använder en huvudplan för att beräkna varor. Om du vill att huvudplanen inkluderar anbudsförfrågansrader som förväntad inleverans, måste du konfigurera detta beteende i inställningarna av huvudplaneringen.  

Som inköpschef eller inköpsagent kan du skapa och underhålla begärandetyper för att matcha anskaffningskraven för din organisation. Varje typ av begäran kan köra poängmetoder. Poängmetoder består av en uppsättning villkor som kan användas när du poängsätter bud. Du måste ställa in typer av begäran, poängmetoder och poängkriterier på sidorna **Typer av begäran** och **Poängmetod** .

## <a name="creating-and-sending-an-rfq"></a>Skapa och skicka en anbudsförfrågan
Du skapar anbudsförfrågan, väljer leverantörerna som du vill bjuda in till anbudsförfrågan och skickar sedan anbudsförfrågan till leverantörerna. Du kan använda utskriftshantering när du vill skicka anbudsförfråganrapporten, och svarsbladrapporterar till ditt prioriterade mål.  

Du kan skapa en anbudsförfrågan för inköpstyperna **Inköpsorder** eller **Inköpsavtal**.  

Om anbudsförfrågan skapas från en inköpsrekvisition, tilldelas typen **Inköpsrekvisition** automatiskt. Du kan inte att skapa en anbudsförfrågan av typen **Inköpsrekvisition**. Om anbudsförfrågan är av typen **Inköpsorder**:

-   När anbudsförfrågansrader skapas, skapas lagertransaktioner som har inleveransstatus **Offert inleverans**.
-   När du accepterar ett bud, skapas en inköpsorder.

Om anbudsförfrågan är av typen **Inköpsavtal**:

-   Anbudsförfrågan används för att köpa en visst kvantitet eller värde av produkten över tid. Du måste välja det datumintervall som gäller för inköpsavtalet och namnet på personen, som hanterar inköpsavtalet.
-   När du accepterar ett bud, skapas ett inköpsavtal.

Du kan endast skapa en anbudsförfrågan från en inköpsrekvisition om statusen på inköpsrekvisitionen är **Under granskning **och du har tilldelats att göra nästa arbetsflödesuppgift. Raderna uppdateras automatiskt i inköpsrekvisitionen allt eftersom du accepterar rader i anbudsförfrågansvar (bud) som du får från leverantörer. Du kan inte slutföra, avvisa, godkänna eller utföra några andra åtgärder på inköpsrekvisitionen medan anbudsförfrågningen pågår.  

När du skapar en anbudsförfrågan, kan du välja en specifik typ av begäran. Typ av begäran bestämmer uppsättning med poängkriterier som används för att poängsätta svar på anbudsförfrågan.  

Du kan lägga till en enkät till ett anbudsförfrågansärende. Denna enkät visas sedan på alla svar, efter att du har skickat anbudsförfrågan.  

Det finns tre sätt att markera leverantören som du vill lägga till ett anbudsförfrågansärende:

-   Lägg till leverantörerna en i taget.
-   Sök efter alla leverantörer som uppfyller vissa kriterier.
-   Lägg automatiskt till alla leverantörer som har godkänts för anskaffningskategorierna, som används på anbudsförfrågansraderna.

När anbudsförfrågansärendet är tomt, klickar du på. **Skicka** Ågärden Skicka skapar journaler och rapporter som ska skrivas ut, arkiveras och skickas enligt dina inställningar för utskriftshantering.  

Om du markerade kryssrutorna **Använd leverantör för omberäkning av priser** och **Använd leverantörsspecifik artikelinformation** på sidan **Skicka anbudsförfrågan** när du skickade förfrågan till leverantörer, anges viss leverantörsspecifik information automatiskt. Du kan ändra den här informationen på sidan **Anbudsförfrågansvar**.  

Följande tabell visar statusändringar för anbudsförfrågan när du skapar en anbudsförfrågan och skickar den till leverantörer.

|                                    |                              |                                                 |                            |                             |
|------------------------------------|------------------------------|-------------------------------------------------|----------------------------|-----------------------------|
| **Action**                         | **Lowest RFQ header status** | **Highest RFQ header status**                   | **Lowest RFQ line status** | **Highest RFQ line status** |
| Skapa sidhuvud och rad för anbudsförfrågan.    | Skapad                      | Skapad                                         | Skapad                    | Skapad                     |
| Skicka anbudsförfrågan till en viss leverantör. | Skickat                         | Skickat                                            | Skickat                       | Skickat                        |
| Lägg till en leverantör.                | Skapad                      | Skickat (anbudsförfrågan har endast skickats till en leverantör). | Skapad                    | Skickat                        |
| Skicka anbudsförfrågan till den andra leverantören. | Skickat                         | Skickat                                            | Skickat                       | Skickat                        |

**Obs!** Du kan lägga till fler leverantörer i en anbudsförfrågan när som helst, och den lägsta och högsta statusvärdena ändras så att den avspeglar de nya leverantörerna. Om du till exempel har fått anbud från alla godkända leverantörer och accepterat minst en rad i ett anbud är den lägsta statusen i anbudsförfrågningens **Avvisade**  och den högsta statusen är **Godkända**. Om du lägger till en ny leverantör, är det lägsta statusvärdet för en rad nu **Skapad**. Därför ändras lägsta status för rubriken för anbudsförfrågan till **Skapad** och högsta status förblir **Godkänd**.

## <a name="amending-an-rfq"></a>Ändra en anbudsförfrågan
Ibland måste du ändra en anbudsförfrågan, efter att du har skickat den. Detta kan hända eftersom till exempel leveransdatum har ändrats, eller du vill ha ytterligare produkter eller olika kvantiteter av produkter. Du kan konfigurera ändringsprocessen, så att den antingen är mer begränsad eller mindre begränsad.  

Om du använder den mer begränsade ändringsprocessen, måste du klicka på **Skapa** på anbudsförfrågansärendet för att starta en ändring, innan du kan ändra fälten på anbudsförfrågansärendet. När du är klar med ändringarna, måste du klicka på **Slutför**. Du kan sedan guidas igenom processen att lägga till information för det e-postmeddelande som skickas för att meddela leverantörer om ändringen. Den uppdaterad anbudsförfråganrapporten som innehåller ett ändringsmeddelande som automatiskt bifogas till meddelandet.  

Om du använder den mindre begränsade ändringsprocessen, behöver du inte skapa en ändring, innan du kan ändra fälten på ett anbudsförfrågansärende som redan har skickats. Du måste dock manuellt lägga till ett ändringsmeddelande på anbudsförfrågan.

## <a name="receiving-and-registering-rfq-replies"></a>Ta emot och registrera svar på anbudsförfrågningar
När du skickar en anbudsförfrågan, skapas ett svarsblad automatiskt. När du får svar på en anbudsförfrågan (bud) måste du ange information från varje leverantör i ett leverantörsspecifikt svarsblad för anbudsförfrågan. Om du har lagt poängkriterier kan du poängsätta svaren. Du kan också jämföra leverantörbuden, genom att rangordna dem enligt dina göra poäng kriterier, till exempel bästa totalt pris eller total bästa leveranstid.  

Om en enkät är kopplad till anbudsförfrågansärendet måste du föra in svaren på frågorna i svarsbladet.  

Om du måste ange alternativrader och anbudsförfrågansärendet tillåter detta, kan du på snabbfliken **Inköpsrekvisitionsrader** klicka på **Lägg till rad**. Ange sedan information om produkten, till exempel artikelnummer eller anskaffningkategori, kvantitet, pris och rabatt.  

Om du har angett ett svar men kräver ett nytt erbjudande från leverantören kan du skicka Anbudsförfrågan. Detta genererar en ny journal och rapporten som du kan använda för att begära ändringar från leverantören.  

Du kan se en översikt över alla anbudsförfrågan och deras svarsstatus på sidan **Anbudsförfråganuppföljning**.  

Följande tabell visar hur anbudsförfråganstatus ändras allt eftersom du tar emot bud och registrerar informationen i anbudsförfrågansvarsbladet.

|                                                |                       |                        |                              |                               |                            |                             |
|------------------------------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Action**                                     | **Lowest bid status** | **Highest bid status** | **Lowest RFQ header status** | **Highest RFQ header status** | **Lowest RFQ line status** | **Highest RFQ line status** |
| Registrera en leverantörs bud och spara det.        | Skickat                  | Mottagen               | Skickat                         | Mottagen                      | Skickat                       | Mottagen                    |
| Registrera den andra leverantörens bud och spara det. | Mottagen              | Mottagen               | Mottagen                     | Mottagen                      | Mottagen                   | Mottagen                    |

**Obs!** Om du returnerar ett bud till en leverantör för ytterligare förhandlingar är både den högsta och den lägsta statusen fortfarande **Inlevererad**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Godkänn och avvisa anbud och överför godkända anbud till underordnade dokument

När du har identifierat det bästa budet, till exempel det bud som erbjuder det bästa totalpriset, accepterar du budet. Status för svaret för anbudsförfrågan för den leverantören uppdateras till **Godkända**. När du accepterar ett bud, eller specifika rader i ett bud, skapas en inköpsorder eller ett inköpsavtal automatiskt, och du kan avvisa buden från de andra leverantörerna.  

När du accepterar ett svar på en anbudsförfrågan av typen **Inköpsrekvisition** uppdateras raderna på inköpsrekvisitionen med följande information från svarsraderna på anbudsförfrågan:

-   Enhetspris
-   Rabattprocent
-   Rabattbelopp
-   Inköp, avgifter
-   Radavgifter
-   Säljare
-   Externt nummer
-   Extern beskrivning

I svaret kan du lägga till en orsakskod för att förklara varför du accepterade eller avvisade ett bud.  

Du kan acceptera alla rader i ett bud och avvisa andra. Du kan också ta emot rader från olika leverantörer. Var medveten om att du bara godtar några rader, ska du uppmanas att avvisa alla andra rader. Därför om du vill ta emot andra rader måste du klicka på **Avbryt** när du tar emot bekräftelsen.  

Följande tabell visar hur anbudsförfråganstatus ändras allt eftersom du godtar och avvisar leverantörernas bud.

|                         |                       |                        |                              |                               |                            |                             |
|-------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Action**              | **Lowest bid status** | **Highest bid status** | **Lowest RFQ header status** | **Highest RFQ header status** | **Lowest RFQ line status** | **Highest RFQ line status** |
| Acceptera ett av buden. | Mottagen              | Godkänt               | Mottagen                     | Godkänt                      | Mottagen                   | Godkänt                    |
| Avvisa de andra buden.  | Avvisad              | Godkänt               | Avvisad                     | Godkänt                      | Avvisad                   | Godkänt                    |




