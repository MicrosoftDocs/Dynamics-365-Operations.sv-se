---
title: Anbudsförfrågningar (RFQ) – översikt
description: Det här ämnet ger en översikt över anbudsförfrågningar (RFQ). Organisationer utfärdar anbudsförfrågan (RFQ) när de vill ta emot konkurrenskraftiga erbjudanden för de artiklar eller tjänster som de måste köpa.
author: mkirknel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage, BOMExpandPurchRFQ, PurchRFQReplyFollowupItem, PurchRFQCaseVend, PurchRFQReplyFollowup, PurchRFQCaseAmendmentInfo, PurchRFQReplyFollowupCase, PurchRFQReplyStatus, PurchRFQCaseReplyFields, PurchRFQAddQuestionnaire, PurchRFQAmendmentWizard, PurchRFQReplyTableStatus, PurchRFQReplyTableListPage, PurchRFQCancelWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd0ee376da52dc3b36ec32859283a410e5b71854
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438082"
---
# <a name="requests-for-quotation-rfqs-overview"></a>Anbudsförfrågningar (RFQ) – översikt

[!include [banner](../includes/banner.md)]

Det här ämnet ger en översikt över anbudsförfrågningar (RFQ). Organisationer utfärdar anbudsförfrågan (RFQ) när de vill ta emot konkurrenskraftiga erbjudanden för de artiklar eller tjänster som de måste köpa. I en anbudsförfrågan ber du leverantörer att ge priser och leveranstiderna för de kvantiteter av artiklar du anger.
Du kan också be leverantörerna att ange om det finns några tillfälliga avgifter, till exempel fraktkostnader, eller om leverantören erbjuder rabatter för stora order eller tidig betalning av leverantörsfakturan.

Anbudsförfråganprocessen består av följande uppgifter:

1. Skapa och skicka en anbudsförfrågan till en eller flera leverantörer
1. Ta emot och registrera bud (svar på anbudsförfrågningar)
1. Överföra bud som du accepterar till en inköpsorder, ett inköpsavtal eller en inköpsrekvisition.

Följande bild ger en översikt över ändringarna i anbudsförfrågansprocessen.

[![RFQ-process](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

Du kan skapa ett anbudsförfrågansärende från planerade order, från en inköpsrekvisition eller genom en manuell post. Anbudsförfrågansärendet är det grundläggande dokument som du använder för att skicka en anbudsförfrågan till varje leverantör.

När du förbereder anbudsförfrågansärende och lägger till leverantörer väljer du **Sskicka** (**Sskicka och publicera** för offentliga sektorn) på anbudsförfrågansärendet. En journal för anbudsförfrågan skapas för varje leverantör som du har skickat anbudsförfrågan till. Du kan konfigurera utskriftsinställningarna för Skicka-åtgärden om du vill skriva ut en rapport för varje leverantör till ett arkiv, eller skicka en rapport varje leverantörs e-postadress. Dessutom kan du använda anbudsförfråganjournalen för varje leverantör för att generera en rapport som du kan skicka eller skicka om till en leverantör senare. Du kan även konfigurera åtgärden Skicka till att skapa ett svarsblad som leverantören kan fylla i.

Nedan beskrivs processen för hantering av anbudsförfrågningar när leverantörsamarbete inte används. Om systemet är inställt för leverantörssamarbete kan leverantörer ange bud direkt i Supply Chain Management. För mer information, se [Leverantörssamarbeten med kunder](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations) och [Leverantörssamarbeten med externa leverantörer](vendor-collaboration-work-external-vendors.md).

Om du måste ändra en anbudsförfrågan när du har skickat den, kan du skicka anbudsförfrågan igen till leverantörer när du är klar med ändringen av två åtgärder: skapa och färdigställ.

När du tar emot bud via e-post kan du hantera desssa bud från sidan **Anbudsförfrågningar**.

Om en andra iteration av ett svar från en leverantör krävs, välj **Retur** på sidan **Anbudsförfrågan**. Returåtgärden skapar en ny journal och en rapport som ska skrivas ut, arkiveras och skickas enligt dina inställningar för utskrift.

Om du har lagt till poängkriterier i ditt anbudsförfrågansärende kommer anbudsförfrågan att ha en poängpanel där du kan ange poängen. Det totala resultatet visas på anbudsförfrågan när du jämför svar på sidan **Jämför svar**. På sidan **Jämför svar** kan du jämföra andra svarsinformation som t.ex. radpris, leveransdatum och totalpris.

När du väljer ett anbud eller ett antal rader i ett anbud kan du acceptera alla eller några rader och avvisa resten. Acceptansjournaler, avvisningsjournaler och motsvarande rapporter genereras och kommer att skrivas ut, arkiveras och skickas enligt dina inställningar för utskrift. När du accepterar ett bud eller specifika rader i ett bud, skapas antingen ett inköpsavtal eller en inköpsorder, eller så uppdateras en inköpsrekvisition beroende på inköpstypen för anbudsförfrågan. Du kan skapa ett handelsavtal som du kan använda senare för någon av svaren, oavsett om du accepterade eller avvisade dem.

Ett anbudsförfrågansärende har två statusar: lägst och högst, du kan visa status på listsidan för **Alla anbudsförfrågningar**. Lägsta status är den minst avancerade fasen för vilken rad som helst i ett anbudsförfrågansärende, och den högsta statusen är den mest avancerade fasen för anbudsförfrågansärendet. Anta exempelvis att ett anbudsförfrågansärende med tre rader skickas till två leverantörer så att det finns två anbudsförfrågningar var med tre rader. Alla rader är **skickade**. Nu registreras ett anbud från en av leverantörerna och anbudsraderna får status **mottagna**. Detta innebär att från de tre raderna i anbudsförfrågansärendet är **skickade** för en anbudsförfrågan och **mottagna** för en annan anbudsförfrågan. Det lägsta statusvärdet blir sedan **skickade,** och högsta status är **mottagna.**

Dessa statusar kommer att beskrivas mer utförligt i detta ämne.

## <a name="setting-up-rfq-functionality"></a>Ställa in funktionen för anbudsförfrågan

Innan du kan skapa ett anbudsförfrågansärende måste du ställa in information om anbudsförfrågan på sidan **Anskaffnings- och källparametrar**. När du skapar ett anbudsförfrågansärende kan du ange förvalda värden som kopieras till anbudsförfrågan. Du kan ange följande standardvärden:

- Inköpstypen av nya anbudsförfrågan: **Inköpsorder** eller **Inköpsavtal**
- Utgångsdatum och tidsförskjutning från dagen då anbudsförfrågansärendet har skapats.
- Typ av begäran kan som standard kan en viss poängmetod till anbudsförfrågansärendet.
- Leveransinformation och betalningsvillkor.

Du kan åsidosätta dessa värden för ett visst anbudsförfråganärende.

Du bör också konfigurera ändringsprocessen. Som en del av den här konfigurationen kan du aktivera låsning av fält. När låsning av fält aktiveras, måste en prokurist som vill ändra en anbudsförfrågan, först välja **Skapa** i avsnittet **Rättelse** på fältet **Offert** på anbudsförfrågansärendet. Sedan när anbudsförfrågan har uppdaterats med ändringarna måste anskaffningsproffset slutföra processen genom att välja **Slutför**. Åtgärden Slutför genererar ett e-postmeddelande som meddelar leverantörer om den ändrade anbudsförfrågan.

På sidan **Anskaffnings- och källparametrar** väljer du mallen för e-postmeddelandet som du ska använda för att skicka till leverantörer. När en mall skapas i **E-postmallar** kan den innehålla följande utbytestoken:

- %Anbudsförfrågansärende%
- %Orsak till att buden returneras%
- %Orsak till ändring%
- %Ändringen har förberetts av%
- %Företag%
- %anbudsförfrågansärendets namn%
- %Utgångsdatum%
- %Datum%

Token för %Orsak till att buden returneras% och %Orsak till ändring% ersätts av text som prokuristen kan ange, när han eller hon avslutar ändringen i guiden **Ändring**. Värdena för token %Ändring förberedd av%, och %Företag% hämtas automatiskt från anbudsförfrågan. Token %Datum% ersätts av det innevarande datumet.

Om du vill avbryta en anbudsförfrågan när den har skickats, kan du göra detta från anbudsförfrågansärendet. För annullering krävs en e-postmall för att skicka meddelande om annullering till leverantörens kontaktpersoner. Mallen måste markeras på sidan **Anskaffnings- och källparametrar**. När mallen skapas, kan den innehålla följande utbytestoken:

- %Orsak till annullering%
- %Anbudsförfrågansärende%
- %Anbudsförfrågan annullerad av%
- %Företag%
- %anbudsförfrågansärendets namn%
- %Datum%

Token %Orsak till annulleringen% ersättas med text som anskaffningsproffset kan ange i guiden **annullering**. Token %Datum% ersätts av det innevarande datumet.

Om du vill använda orsakskoder för ett anbud för att ange varför det accepterades eller avvisades, måste du ställa in orsakskoder på sidan **Leverantöranledningar**.

Du kan konfigurera utseendet på dina utskrivna eller lagrade anbudsförfrågandokument på sidan **Formulärinställningar** i anskaffning och källa.

> [!NOTE]
> För en konfiguration av offentliga sektorn i en anbudsförfrågan som redan har skickats kräver användning av en ändringsprocessen. När en anbudsförfrågan har skickats är fälten låsta.
Om du vill ändra anbudsförfrågan måste du därför välja **Skapa** för att starta ändringsprocessen, enligt beskrivningen ovan. Låsningssättet kontrolleras av alternativet **Lås anbudsförfrågan när de har skickats** på sidan **Anskaffnings- och källparametrar**. Denna parameter är som standarad inställd på **Ja** och för en konfiguration av offentlig sektor kan standardinställningen inte ändras. Därför, även om ändringsprocessen kan hanteras manuellt i en konfiguration av icke offentlig sektor måste den användas för en konfiguration av offentlig sektor.

När du skapar ett anbudsförfrågansärende av typen inköpsorder och lägger till en lagerartikel för anbudsförfrågan, skapas en lagertransaktion som har inleveransstatusen **Offert inleverans**. Endast rader i ett anbudsförfrågansärende som har denna status beaktas när du använder en huvudplan för att beräkna varor. Om du vill att huvudplanen inkluderar rader i ett anbudsförfrågansärende som förväntad inleverans, måste du konfigurera detta beteende i inställningarna av huvudplaneringen.

En inköpschef eller inköpsagent kan skapa och underhålla begärandetyper för att matcha anskaffningskraven för din organisation. Varje typ av begäran kan associeras med en poängmetod. Poängmetoder består av en uppsättning villkor som kan användas när du poängsätter bud. Du måste ställa in typer av begäran, poängmetoder och poängkriterier på sidorna **Typer av begäran** och **Poängmetod** .

## <a name="choose-default-fields-to-include-in-vendor-rfq-reply-forms"></a><a name="default-reply-fields"></a>Välj standardfält som ska inkluderas i svarsformulär för leverantörsanbud

Du kan ange specifika typer av information som leverantörerna ska lämna när de svarar på (lägger bud) en anbudsförfrågning. Fält som du markerar som standard inkluderas i det online-formulär som används för leverantörssamarbete. För att ändra dessa inställningar:

1. Om du inte redan har gjort det använder du sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera fälten *Välj fält som ska inkluderas i svarsformulär för leverantörsanbud*.
1. Gå till **Anskaffning och källa > Inställningar > Anskaffnings- och källparametrar**.
1. Öppna fliken **Anbudsförfrågan**.
1. Välj svarsfältets länk **standard anbudsförfrågan** under rubriken **ställ in standardvärden för anbudsförfrågan**.
1. Dialogrutan **Standardsvarsfält för anbudsförfrågan** öppnas.
1. Avsnittet **anbudsfält som inkluderade i svarsformulär för leverantörsanbud** innehåller ett skjutreglage för varje fält som kan användas i svarsformulären för en anbudsförfrågan. Fält inställda på *Ja* i det här avsnittet kommer att inkluderas (tillsammans med deras värden) i svarsformulär för anbudsförfrågan. Ställ in skjutreglaget till *Nej* för varje fält där du vill förhindra att leverantörer ser data när de granskar anbud. På så sätt kan du ange uppskattade eller förväntade värden under posten för anbudsförfrågan för interna behov utan att leverantören ser vad som har angetts.

Du kan åsidosätta inställningarna för enskilda anbudsförfrågningar efter behov.

## <a name="creating-and-sending-an-rfq"></a>Skapa och skicka en anbudsförfrågan

Du skapar ett anbudsförfrågansärende, väljer leverantörerna som du vill bjuda in till anbudsförfrågansärendet och skickar sedan anbudsförfrågan till leverantörerna. Du kan använda utskriftsinställningar när du vill skicka anbudsförfråganrapporten, och svarsbladrapporterar till ditt prioriterade mål.

Du kan manuellt skapa ett anbudsförfrågansärende för antingen inköpstyperna **Inköpsorder** eller **Inköpsavtal**.

Om anbudsförfrågansärendet är av typen **inköpsorder** sker följande beteende som avviker från andra typer av anbudsförfrågansärenden:

- När rader för anbudsförfrågansärende skapas, skapas lagertransaktioner som har inleveransstatus **Offert inleverans**.
- När du accepterar ett bud, skapas en inköpsorder.

Om anbudsförfrågan är av typen **inköpsavtal** sker följande beteende som avviker från andra anbudsförfrågansärenden:

- Anbudsförfrågansärendet används för att köpa en visst kvantitet eller värde av produkten över tid. Du måste välja det datumintervall som gäller för inköpsavtalet och namnet på personen, som hanterar inköpsavtalet.
- När du accepterar ett bud, skapas ett inköpsavtal.

Om anbudsförfrågansärendet skapas från en inköpsrekvisition, tilldelas typen **Inköpsrekvisition** automatiskt. Du kan inte att skapa ett anbudsförfrågansärende av typen **Inköpsrekvisition**.

Du kan endast skapa ett anbudsförfrågansärende från en inköpsrekvisition om statusen på inköpsrekvisitionen är **Under granskning** och du har tilldelats att göra nästa arbetsflödesuppgift. Raderna uppdateras automatiskt i inköpsrekvisitionen allt eftersom du accepterar rader från anbud (anbudsförfrågansvar) som du får från leverantörer. Du kan inte slutföra, avvisa, godkänna eller utföra andra åtgärder på inköpsrekvisitionen förrän rekvisitionsraden uppdateras med en godkänd anbudsförfrågansrad eller om anbudsförfrågansärendet har annullerats.

När du skapar ett anbudsförfrågansärende, kan du välja en typ av begäran. Typ av begäran bestämmer uppsättning med poängkriterier som används för att poängsätta svar på anbudsförfrågningar för anbudsförfrågansärendet.

Du kan lägga till en enkät till ett anbudsförfrågansärende. Denna enkät visas sedan på alla svar på anbudsförfrågningar, efter att du har skickat anbudsförfrågan. Ifyllandet av enkäten är en obligatorisk uppgift innan anbudet kan skickas.

Även om standardvärden har angetts kan du ändra inställningarna för **anbudsfält som inkluderade i svarsformulär för leverantörsanbud** för varje enskild anbudsförfrågan om det behövs. Det gör du genom att skapa eller öppna ett ärende för anbudsförfrågan. Öppna sedan fliken **Offert** i åtgärdsfönstret och från avsnittet **Svar** välj **Ange standardsvar för anbudsförfrågan**. Dialogrutan **Standardsvarsfält för anbudsförfrågan** öppnas, vilket fungerar på samma sätt som när du ställer in standardvärdena för svarsformulär för leverantörsanbud, förutom att dina ändringar här bara påverkar det aktuella anbudsförfrågansärendet. Mer information om hur du aktiverar den här funktionen och hur den fungerar finns i [Välj standardfält som ska inkluderas i svarsformulär för leverantörens anbudsförfrågningar](#default-reply-fields).

Det finns tre sätt att markera leverantören som du vill lägga till ett anbudsförfrågansärende:

- Lägg till leverantörerna en i taget.
- Sök efter alla leverantörer som uppfyller vissa kriterier.
- Lägg automatiskt till alla leverantörer som har godkänts för anskaffningskategorierna, som används på rader i ett anbudsförfrågansärende.

När anbudsförfrågansärendet är tomt, väljer du **Skicka** Ågärden Skicka skapar journaler och rapporter som ska skrivas ut, arkiveras och skickas enligt dina utskriftsinställningar.

Om du anger **Använd leverantör för omberäkning av priser** och **Använd leverantörsspecifik artikelinformation** till **Ja** på sidan **Skicka anbudsförfrågan** när du skickade anbudsförfrågan till en leverantör, anges viss leverantörsspecifik information i anbudsförfrågan för den leverantören automatiskt.

## <a name="amending-an-rfq-case"></a>Ändra ett anbudsförfrågansärende

Ibland måste du ändra ett anbudsförfrågansärende efter att du har skickat det. Du kanske måste ändra ett anbudsförfrågansärende om till exempel leveransdatum har ändrats, eller du vill ha ytterligare produkter eller olika kvantiteter av produkter. Du kan konfigurera ändringsprocessen, så att den antingen är mer begränsad eller mindre begränsad.

Om du konfigurerar ändringsprocessen till att vara mer restriktiv måste du innan du kan ändra fälten i ett ärende i anbudsförfrågan som redan har skickats välja **Skapa** på anbudsförfrågansärendet innan en ändring av anbudsförfrågan. När du är klar med ändringarna, måste du klicka på **Slutför**. Du kan sedan guidas igenom processen att lägga till information för det e-postmeddelande som skickas för att meddela leverantörer om ändringen. Den uppdaterad anbudsförfråganrapporten som innehåller ett ändringsmeddelande som automatiskt bifogas till e-postmeddelandet.

Om du konfigurerar ändringsprocessen så att den blir mindre restriktiv behöver du inte välja **Skapa** innan du kan ändra fälten på ett anbudsförfrågansärende som redan har skickats. Du måste dock manuellt lägga till ett ändringsmeddelande på anbudsförfrågan och skicka ärendet igen. Tänk på att denna metod endast kan användas om inget svar (bud) har redigerats. Om du har angett ett svar och det befinner sig status **mottagen** är knappen **skicka** inte tillgänglig. I det här fallet måste du välja **skapa** och **slutför** såsom du måste göra i den mer restriktiva processen. Svaret återställs sedan till att återspegla ändringarna i anbudsförfrågansärendet.

Om leverantörer använder gränssnittet för leverantörssamarbete måste du alltid använda ändringsprocessen för att meddela leverantörer om ändringar av anbudsförfrågansärendet. Denna process hjälper till att förhindrar situationen där leverantörer lägger bud på ett inaktuellt anbudsförfrågansärende när deras bud pågår. För mer information om leverantörssamarbetet, se [Leverantörssamarbeten med externa leverantörer](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-external-vendors).

Om du vill bjuda in ytterligare leverantörer till att lämna bud, och inga ändringar har gjorts i anbudsförfrågansärendet kan du använda knappen **skicka**. De leverantörer som du lade till visas på sidan **skicka** och kommer att ta emot e-postinbjudan.

## <a name="receiving-and-registering-rfq-replies"></a>Ta emot och registrera svar på anbudsförfrågningar

När du skickar en anbudsförfrågan, skapas ett svarsblad automatiskt. När du tar emot bud på en anbudsförfrågan, måste du ange dem via sidan **Anbudsförfrågan** genom att klicka på åtgärden **Redigera svar på anbudsförfrågan.** Här kan du ange information om budet i ett särskilt budformulär. Först kommer **Svarsförlopp** att vara **Ej startat**. När du klickar på **Redigera svar på anbudsförfrågan** är förloppsstatus **Inköparen uppdaterar** tills budet har skickats. Klicka på **skicka** när du har angett informationen om budet. Svarsförloppets status ändras till **Skickad av inköparen.** På samma sätt med leverantörssamarbete aktiverat, kommer **Svarsförloppet** att uppdateras när leverantören samverkar med budet. Därefter ändras status från **Leverantör uppdateras** till **Skickad av leverantör**. När erbjudandet skickas skapas en journal som **Mottagen**. Svaret (budet) måste skickas för att registreras som inlevererad och först därefter kan det behandlas ytterligare som accepterat eller avvisat.

Om du behöver uppdatera budet bör du gå igenom samma process som ovan och skicka på nytt.

Observera att det endast är tillåtet att redigera formuläret **Anbudsförfrågan** för information relaterad till behandling av budet, inte för att registrera budet. Klicka på **Redigera svar på anbudsförfrågan** om du vill registrera eller ändra budet.

När du anger budinformationen och om anbudsförfrågansärendet tillåter alternativa rader, kan du lägga till alternativa rader för rader som endast har en upphandlingskategori och inget specificerat katalogobjekt. Klicka på **Lägg till alternativ** för att lägga till alternativa rader.

Om du har angett ett svar men kräver ett nytt erbjudande från leverantören kan du returnera anbudsförfrågan. En ny journal och en rapport skapas, som kan skickas till leverantören.

Du kan se en översikt över alla anbudsförfrågan och deras status: **Skickat, Mottaget, Godkänt, Avvisat, Avbrutet, Avböjt** på sidan **Uppföljning av anbudsförfrågan**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Godkänn och avvisa anbud och överför godkända anbud till underordnade dokument

När du har identifierat det bästa budet, till exempel det bud som erbjuder det bästa totalpriset, accepterar du budet. Du kan acceptera alla rader i ett bud och avvisa andra.
Du kan också ta emot rader från olika leverantörer. Var medveten om att du bara godtar några rader, ska du uppmanas att avvisa alla andra rader. Därför om du vill ta emot andra rader måste du välja **Avbryt** när du uppmanas. Status för svar på anbudsförfrågan för varje leverantör som accepterar bud eller rader från uppdateras till **accepterade**.

Om du, när du förbereder inköpsordern eller inköpsavtal, måste lägga till ytterligare en rad i anbudsförfrågan, kan du göra det genom att klicka på **Lägg till rad** på radrutnätet **Anbudsförfrågan**. Du kan bara visa och ändra den här raden på sidan **Anbudsförfrågan**. Den kommer att visas på budsidan när den har accepterats.

När du accepterar ett bud, eller en eller felra rader i ett bud, skapas en inköpsorder eller ett inköpsavtal automatiskt. Du kan sedan avvisa bud från andra leverantörer.

I svaret kan du lägga till en orsakskod för att förklara varför du accepterade eller avvisade ett bud.

När du accepterar ett bud av typen **Inköpsrekvisitioner** kommer inköpsrekvisitionsraderna att uppdateras med följande information som visar information om det godkända budet:

- Pris per enhet
- Rabattprocent
- Rabattbelopp
- Inköp, avgifter
- Radavgifter
- Leverantör
- Externt nummer
- Extern beskrivning

Följande tabell visar hur anbudsförfråganstatus ändras allt eftersom du godtar och avvisar leverantörernas bud.

## <a name="statuses--highest-and-lowest"></a>Status – högsta och lägsta

På fliken Leverantör i anbudsförfrågansärendet visas raderna som har det högsta och det lägsta statusvärdet för en viss leverantör. När leverantören läggs till och inga rader ännu har skickats, <strong>skapas</strong> både den lägsta och den högsta statusen. När anbudsförfrågan skickas till leverantören med alla rader kommer status för de två raderna att <strong>skickas</strong>. Om vissa rader i ett bud från en leverantör accepteras och andra avvisas kommer de avvisade raderna att visa den lägsta status som är <strong>avvisad</strong> och de godkända raderna får den högsta status som är <strong>accepterade</strong>.

På raderna för anbudsförfrågansärendet ser du det högsta och det lägsta statusvärdet per rad över alla leverantörer. Om du har skickat en rad till alla leverantörer i anbudsförfrågansärendet och ingen har svarat ännu är både lägsta och högsta status **skickad.** När minst en leverantör svarar ändras det högsta status till **mottagna**. Om du lägger till en ny leverantör till ärendet kommer det lägsta statusvärdet att ändras till **Skapad**

Den högsta och lägsta status för anbudsförfrågansärendet är en sammansättning av status på fliken \<Leverantör och fliken Rader.

Status rangordnas på följande sätt från lägsta till högsta: skapad, skickad, mottagen, avvisad, accepterad, avböjd, annullerad.

Följande tabell visar statusändringar för anbudsförfrågansärendet när du skapar ett anbudsförfrågansärendet och skickar det sedan till leverantörer.

| **Åtgärd**                                | **Lägsta status för anbudsförfrågansärende** | **Högsta status för anbudsförfrågansärende** | **Lägsta status för anbudsförfrågansärenderad** | **Högsta status för anbudsförfrågansärenderad** |
|-------------------------------------------|----------------------------|-----------------------------|---------------------------------|----------------------------------|
| Skapa sidhuvud och rad för anbudsförfrågansärende.      | Skapades                    | Skapades                     | Skapades                         | Skapades                          |
| Skicka anbudsförfrågningar till alla leverantörer i anbudsförfrågansärendet. | Har skickats till                       | Har skickats till                        | Har skickats till                            | Har skickats till                             |
| Lägg till en leverantör.                       | Skapades                    | Har skickats till                        | Skapades                         | Har skickats till                             |
| Skicka anbudsförfrågan till den andra leverantören.        | Har skickats till                       | Har skickats till                        | Har skickats till                            | Har skickats till                             |

Alla rader på de anbudsförfrågningar som hör till anbudsförfrågansärendet får status **skickad**.

Följande tabell visar hur anbudsförfråganstatus ändras allt eftersom du tar emot bud och registrerar informationen i anbudsförfrågansvarsbladet.

| **Åtgärd**                                               | **Lägsta status över alla rader på alla anbudsförfrågningar.** | **Högsta status över alla rader på alla anbudsförfrågningar.** | **Lägsta status för anbudsförfrågansärendehuvud** | **Högsta status för anbudsförfrågansärendehuvud** | **Lägsta status för anbudsförfrågansärenderad** | **Högsta status för anbudsförfrågansärenderad** |
|----------------------------------------------------------|------------------------------------------------|-------------------------------------------------|-----------------------------------|------------------------------------|---------------------------------|----------------------------------|
| Registrera en leverantörs bud på en anbudsförfrågan och spara det.        | Har skickats till                                           | Inlevererat                                        | Har skickats till                              | Inlevererat                           | Har skickats till                            | Inlevererat                         |
| Registrera den andra leverantörens bud till en anbudsförfrågan och spara det. | Inlevererat                                       | Inlevererat                                        | Inlevererat                          | Inlevererat                           | Inlevererat                        | Inlevererat                         |


I exemplet nedan du ser högsta/lägsta status på anbudsförfrågansärenden där ett bud har tagits emot och andra bud har accepterats. När ett mottaget bud avvisas kommer lägsta status att ändras från mottaget till avvisat på anbudsförfrågansärendets sidhuvud och rad.


|            <strong>Åtgärd</strong>             | <strong>Lägsta status över alla rader på alla anbudsförfrågningar.</strong> | <strong>Högsta status över alla rader på alla anbudsförfrågningar.</strong> | <strong>Lägsta status för anbudsförfrågansärendehuvud</strong> | <strong>Högsta status för anbudsförfrågansärendehuvud</strong> | <strong>Lägsta status för anbudsförfrågansärenderad</strong> | <strong>Högsta status för anbudsförfrågansärenderad</strong> |
|------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------------|------------------------------------------------|-------------------------------------------------|----------------------------------------------|-----------------------------------------------|
| Acceptera ett av buden. (eller minst en rad) |                          Inlevererat                           |                           Accepterade                           |                    Inlevererat                    |                    Accepterade                     |                   Inlevererat                   |                   Accepterade                    |
|           Avvisa alla de andra buden.           |                          Avvisat                           |                           Accepterade                           |                    Avvisat                    |                    Accepterade                     |                   Avvisat                   |                   Godkänt                    |

