---
title: Förbättringar i inköps-cXML
description: Förbättringar i inköps-cXML bygger på den befintliga funktionen för extern katalog, PunchOut, som används för inköpsrekvisitioner.
author: Henrikan
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatCXMLParameters, CatCXMLPurchRequest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-08-03
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 2942b141eb3a5b83fb39b0de721bae60c074e01c
ms.sourcegitcommit: f5885999e008a49fe072d95f15e239905c24918a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900720"
---
# <a name="purchasing-cxml-enhancements"></a>Förbättringar i inköps-cXML

[!include [banner](../includes/banner.md)]

Funktionen _Förbättringar i inköps-cXML_ bygger på [den befintliga funktionen för extern katalog](set-up-external-catalog-for-punchout.md) som används för inköpsrekvisitioner. Den här befintliga funktionen kallas för _PunchOut_. Även om en inköpsorder inte måste utgå från en inköpsrekvisition måste det finnas en koppling mellan leverantören på en inköpsorder och de parametrar som används för att skicka inköpsorderdokumentet.

## <a name="turn-on-the-purchasing-cxml-enhancements-feature"></a>Aktivera funktionen förbättringar i inköps-cXML

Om du vill aktivera funktionen öppnar du sidan **[funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** och söker efter funktionen med namnet *Förbättringar i inköps-cXML*. Välj funktionen och välj sedan **aktivera nu** för att aktivera den. (Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard.)

När du har aktiverat funktionen bör du konfigurera inställningar i följande tre områden:

- **[cXML-parametrar](#cxml-parameters)** – Använd de här inställningarna om du vill ställa in globala parametrar för funktionen för att skicka inköpsorder.
- **[Leverantörsinställningar](#vendor-setup)** – om Commerce EXtensible Markup Language (cXML) ska användas som standard för alla nya inköpsorder som skapas för alla leverantörer, ställer du in alternativet **Skicka inköpsorder via cXML** till _Ja_ för den leverantören.
- **[Externa kataloger](#external-catalog-setup)** – Använd de nya inställningarna för **Orderegenskaper** för att definiera formatet på inköpsorderdokumentet och hur det ska skickas.

I bilden nedan sammanfattas den här konfigurationen.

![Områden för inställning av cXML-funktioner.](media/cxml-settings-areas.png "Områden för inställning av cXML-funktioner")

Du måste dessutom ställa in [Batch-jobbet inköpsorder förfrågan](#po-batch). Det här batch-jobbet används för att skicka bekräftade inköpsorder.

## <a name="set-up-global-cxml-parameters"></a><a name="cxml-parameters"></a>Ställ in globala cXML-parametrar

Använd **cXML-parametrar** för att göra några globala inställningar som gäller för funktionaliteten för att skicka inköpsorder.

![cXML-parametersida.](media/cxml-parameters.png "cXML-parametersida")

Gå till **Anskaffning och källa \> inställningar \> cXML-hantering \> cXML-parametrar** och ange följande parametrar:

- **cXML-testläge** – den här globala parametern påverkar hur inköpsorder fysiskt skickas från batch-jobbet. Välj ett av följande värden:

    - **Test** – i det här läget kan batchjobbet köras och XML-dokumentet för meddelandet genereras, men det skickas inte. I stället sparas det på begäran om inköpsorder i granskningssyfte. Det här läget är användbart när du befinner dig vid en första implementering och du vill se hur data anges i cXML-meddelandet. Du kanske också vill skapa exempelmeddelanden som du kan skicka till leverantörer vid initial validering.
    - **Levande** – i det här läget använder funktionen de [externa kataloginställningarna](#external-catalog-setup) för att fysiskt överföra varje dokument till leverantören.

- **Skicka uppdateringar för inköpsförfrågningar** – Ställ in det här alternativet på *Ja* för att skicka ett uppdateringsmeddelande för inköpsorder. Ställ in den på *Nej* om du inte vill att meddelandet ska skickas. De flesta leverantörer föredrar att inte ta emot uppdateringsmeddelanden. De kräver istället att kunderna kontaktar dem per telefon eller e-post om en inköpsorder ska ändras. Den här parametern är en global parameter och ingen åsidosättning kan anges för varje leverantörs externa katalog. En inköpsorder markeras som uppdaterad om du bokför en andra bekräftelse på en inköpsorder, men den första bekräftelsen har redan skickats och bekräftats av leverantören. Om det finns en andra bekräftelse, men den första bekräftelsen inte har skickats, kommer den andra bekräftelsen att behandlas som ett nytt dokument. Du kan bekräfta en inköpsorder så många gånger du vill, tills en bekräftelse skickas. Nästa bekräftelse kommer sedan att behandlas som ett uppdateringsmeddelande.
- **Skicka radera inköpsförfrågningar** – Ställ in det här alternativet på *Ja* för att skicka ett raderingsmeddelande för inköpsorder. Ställ in den på *Nej* om du inte vill att meddelandet ska skickas. De flesta leverantörer föredrar att inte ta emot raderingsmeddelanden. De kräver istället att kunderna kontaktar dem per telefon eller e-post om en inköpsorder skickades av misstag. Den här parametern är en global parameter och ingen åsidosättning kan anges för varje leverantörs externa katalog. En inköpsorder markeras som borttagen om du avbryter inköpsordern i Supply Chain Management.
- **Arkivfil** – Ange sökvägen till filen där du vill exportera och spara arkiverade cXML-dokument. Sökvägen används när du kör rensningsfunktionen på sidan **Förfrågan om inköpsorder**.
- **Max. tecken för gatuadress** – Ange det högsta antalet tecken som kan användas i gatuadressen för adresser i cXML-dokumentet. Den här globala parametern påverkar alla leverantörer om inte en åsidosättning anges för de externa katalogegenskaperna.

## <a name="set-up-vendor-purchase-orders-to-use-cxml"></a><a name="vendor-setup"></a>Ange inköpsorder för leverantör för att använda cXML

Varje gång du bekräftar en inköpsorder där alternativet **Skicka inköps order via cXML** anges till _Ja_, genererar systemet automatiskt cXML-meddelandet och levererar det till den leverantör som är kopplad till den inköpsordern. Det finns två sätt att kontrollera det här alternativet för dina inköpsorder:

- Om du vill ställa in en leverantör så att den automatiskt använder cXML för alla nya inköpsorder som skapas från en rekvisition, gå till **Anskaffning och källa \> Leverantörer \> Alla leverantörer** och välj eller skapa en leverantör för att öppna sidan med information om sidan. På snabbfliken **Standardvärden för inköpsorder** anger du alternativet **Skicka inköpsorder via cXML** till _Ja_. Om cXML även ska användas automatiskt för nya inköpsorder som **inte** skapas från en rekvisition, måste du också ställa in egenskapen **ENABLEMANUALPO** till _True_ för den relaterade externa katalogen, enligt beskrivningen i [Ange orderegenskaper](#set-order-properties) senare i det här avsnittet.
- För enskilda inköpsorder går du till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder** och väljer eller skapar en inköpsorder för att öppna sidan information om den. Växla till vyn **Huvud** och sedan på snabbfliken **Inställningar** ange alternativet **Skicka inköpsorder via cXML** efter behov.

![Standardinställningar för inköpsorder för leverantör.](media/cxml-order-defaults.png "Standardinställningar för leverantörs inköpsorder")

## <a name="set-up-an-external-catalog-to-use-cxml"></a><a name="external-catalog-setup"></a>Ställ in en extern katalog till att använda cXML

På sidan **Externa kataloger**, för varje katalog, kan du ställa in funktionerna för PunchOut och funktionen för att skicka inköpsorder. Om du vill söka efter relevanta inställningar går du till **Anskaffning och källa \> Kataloger \> Externa kataloger**. Börja med att [ställa in varje katalog som vanligt](set-up-external-catalog-for-punchout.md). Processen omfattar tilldelning av en leverantör, val av de kategorier som leverantören har tillåtelse att leverera och aktiverar katalogen. Konfigurera sedan de ytterligare inställningar som beskrivs i det här avsnittet.

> [!NOTE]
> När du bekräftar en inköpsorder som kan skickas via cXML, letar systemet upp den leverantör som är kopplad till inköpsordern och söker sedan efter den första aktiva externa katalogen som är kopplad till leverantören. Därefter använder systemet de inställningar från den externa katalogen för att skicka inköpsordern. Om flera externa kataloger har ställts in, använder systemet bara den första externa katalogen som den hittar, baserat på leverantören på inköpsordern. Därför rekommenderar vi att du skapar en enda extern katalog för varje leverantör.

![Inställningar för extern katalog.](media/cxml-supplier-catalog.png "Inställningar för extern katalog")

### <a name="set-the-punchout-protocol-type"></a>Ange protokolltyp för PunchOut

På snabbfliken **Allmänt** på sidan **Externa kataloger** ställer du in fältet **Protokolltypen PunchOut** på _cXML_. Det här alternativet är det enda tillgängliga alternativet, såvida inte en partner har utökat funktionen och tillhandahåller ytterligare ett alternativ i tillägget.

Om du också använder katalogen för PunchOut måste du också [ställa in meddelandeformatet](set-up-external-catalog-for-punchout.md). Meddelandeformatet används för att upprätta anslutningen till leverantören i PunchOut-transaktionen från rekvisitionen. När en inköpsorder skickas används orderegenskaperna för att upprätta kopplingen till en leverantör.

### <a name="set-the-order-properties"></a><a name="set-order-properties"></a>Ställ in orderegenskaper

Funktionen _Förbättringar i inköps-cXML_ lägger till snabbfliken **Orderegenskaper** för externa kataloger. På den här snabbfliken finns ett rutnät där du kan definiera orderegenskaperna. Det innehåller också ett verktygsfält. Det här verktygsfältet innehåller följande tre knappar som du kan använda för att hantera orderegenskaper:

- **Standardegenskaper** – om du ställer in en ny katalog väljer du den här knappen om du vill lägga till en fördefinierad samling egenskaper som används ofta i rutnätet.
- **Ny** – Lägg till en ny egenskap i rutnätet.
- **Ta bort** – ta bort den aktuella markerade egenskapen från rutnätet. Om du råkar ta bort en standardegenskap av misstag väljer du **standardegenskaper** för att återställa alla saknade egenskaper.

Varje gång du lägger till en eller flera egenskaper i rutnätet använder du den högra kolumnen för att ange ett värde för varje.

Använd standardegenskaperna på följande sätt:

- **BUYER\_COOKIE** – det här spårningsfältet kan användas för att ange specifik information för ditt företag. Om du inte har ett avtal med leverantören om hur den här egenskapen används, har den ingen mycket stor betydelse när det gäller att skicka en inköpsorder. Därför bör du ställa in det på ett enkelt värde.
- **DELIVERTO** – när leveransadressen anges i dokumentet från inköpsordern används fältet **Varningsinformation** för att ställa in fältet **DELIVERTO** i XML-meddelandet. Om du kräver att det här värdet är ett namn på en beställare och du vill ange fältet beställare i inköpsorderns rubrik, anger du värde _REQUESTER_ för den här egenskapens så att beställarens namn anges i fältet **DeliverTo** i XML. I det här fallet kommer den primära e-postadressen och det telefonnummer som används att hämtas från beställaren istället för beställaren.
- **DEPLOYMENTMODE** – Ange den här egenskapen som krävs av leverantören. Värdena är vanligen _PRODUCTION_ eller _TEST_. Ställ in värdet baserat på kommunikationen med leverantören. Vanligtvis måste den matcha det avsedda systemet bakom värdet **ORDERCHECKURL** som leverantören anger som ett test- eller produktionssystem.
- **FIXEDBILLADDRESSID** – när fältet **addressID** i XML-meddelandet är inställt, hämtar det platsen som är angiven på adressen. Om ID-värdet som du har skickat till leverantören skiljer sig från värdet på adressplatsen av någon anledning, kan du framtvinga en åsidosättning genom att ange värdet här. Antagandet är att du bara kommer att använda en adress med leverantören och att adressen har ställts in i leverantörens system. Faktureringsadressen är den primära fakturaadressen som anges för den juridiska personen i Supply Chain Management.
- **FIXEDSHIPADDRESSID** – när fältet **addressID** i XML-meddelandet är inställt, hämtar det platsen som är angiven på adressen. Om ID-värdet som du har skickat till leverantören skiljer sig från värdet på adressplatsen av någon anledning, kan du framtvinga en åsidosättning genom att ange värdet här. Antagandet är att du bara kommer att använda en adress med leverantören och att adressen har ställts in i leverantörens system. Leveransadressen är adressen som anges i rubriken på inköpsordern. De flesta leverantörer accepterar endast rubrikadresser, inte radadresser. Även om det finns fält för radadresser i XML-koden kommer de att anges som rubrikadress.
- **FROM\_DOMAIN** – Ange det värde som används för att skicka inköpsorderdokument. Det här värdet anges av leverantören.
- **FROM\_IDENTITY** – Ange det värde som används för att skicka inköpsorderdokument. Det här värdet anges av leverantören.
- **ORDERCHECKURL** – Ange den URL som inköpsorderdokumenten ska skickas till. Denna URL börjar med `https://` och tillhandahålls av din leverantör.
- **PAYLOAD\_ID** – Ange ett prefixvärde för det nyttolast-ID som krävs för de affärsprocesser som finns för den aktuella leverantören.
- **SENDER\_DOMAIN** – Ange det värde som används för att skicka inköpsorderdokument. Det här värdet anges av leverantören.
- **SENDER\_IDENTITY** – Ange det värde som används för att skicka inköpsorderdokument. Det här värdet anges av leverantören.
- **SHARED\_SECRET** – Ange det värde som används för att skicka inköpsorderdokument. Det här värdet anges av leverantören.
- **STREETLENGTH** – Ange ett tal som representerar det maximala antalet tecken som leverantören godtar som gatunamn. Om ett värde anges här åsidosätts det värde som anges på sidan **cXML-parametrar**. Systemet tar bort radbrytningar och blanksteg för att passa in standardadressen i Supply Chain Management i det antal tecken som anges här. Alla ytterligare tecken kommer att trunkeras.
- **TO\_DOMAIN** – Ange det värde som används för att skicka inköpsorderdokument. Det här värdet anges av leverantören.
- **TO\_IDENTITY** – Ange det värde som används för att skicka inköpsorderdokument. Det här värdet anges av leverantören.
- **USERAGENT** – Ange ett värde som identifierar systemet du använder. Ange exempelvis _Dynamics 365 Supply Chain Management_.
- **VERSION** – Ange ett cXML versionsnummer om leverantören begär denna information. Standardversionen är *1.2.008*. Den här versionen är stabil och accepteras av de flesta leverantörer.
- **RESPONSETEXT** – ange valfri anpassad text som du tror att leverantören ska returnera i cXML-svarsmeddelandet efter att ordern har skickats. På så sätt kan systemet markera meddelandet som _bekräftat_. Om svaret inte matchar standardtext eller kundtexten som du anger här, markeras förfrågan som ett _fel_.
- **RESPONSETEXTSUB** – Ange den här egenskapen till _TRUE_ om du vill söka efter leverantörens svarstext för de värden som anges i fältet **RESPONSETEXT**. Leverantören kan till exempel returnera en lång sträng som innehåller "OK" i svaret. I det här fallet kan du ange _OK_ i fältet **RESPONSETEXT** och ställa in **RESPONSETESTSUB** på _TRUE_ om du vill söka efter "OK" var som helst i svaret. Ordern kan sedan ställas in på _bekräftad_.
- **CONTENTTYPE** – du behöver inte ställa in den här egenskapen för en typisk kataloginställning. Om du får ett server 500-fel från leverantörens system när du skickar en inköpsorder, kan du utföra tester genom att ge egenskapen värdet _FALSE_. Det värdet kommer att ändra en inställning i webbförfrågningen och kan göra det möjligt att skicka meddelandet för vissa plattformar.
- **ENABLEHEADERS** – Ange den här egenskapen till _TRUE_ för att skicka rubriker tillsammans med inköpsordern. Du måste bara ange den här egenskapen om leverantören kräver det. Om du ställer in den här egenskapen på _TRUE_ lägger du till extra anpassade egenskaper som baseras på de namn som leverantören tillhandahåller och ger dem prefixet _H\__. Typiska exempel är **H\_USERID**, **H\_PASSWORD**, **H\_RECEIVERID** och **H\_ACTIONREQUEST**. Följande anpassade egenskaper ingår i standardegenskaperna:

    - **H\_USERID** – om handelspartnern kräver att du skickar ett användar-ID som en del av URL:en för att skicka en inköpsorder anger du värdet här.
    - **H\_PASSWORD** – om handelspartnern kräver att du skickar ett lösenord som en del av URL:en för att skicka en inköpsorder anger du värdet här.

- **ENABLEMANUALPO** – om den här egenskapen har värdet _TRUE_ och användarna manuellt skapar inköpsorder (dvs. när de inte startar från en rekvisition) ärver dessa inköpsorderinställningen för alternativet **Skicka inköpsorder via cXML** från leverantören. Om den här egenskapen inte anges, eller om den har värdet _FALSE_ kommer alternativet **Skicka inköpsorder via cXML** inte att ställas in i inköpsorderrubriken för manuellt skapade inköpsorder. För inköpsorder som skapas från en rekvisition ärvs inställningen för alternativet **Skicka inköpsorder via cXML** alltid från leverantören, oavsett inställningen för den här egenskapen. Mer information finns i avsnittet [Ställa in leverantörs inköpsorder för att använda cXML](#vendor-setup) tidigare i det här avsnittet.
- **PUNCHOUTPOONLY** – om den här egenskapen har värdet _TRUE_ kommer endast inköpsrekvisitionsrader som skapas från funktionen PunchOut att ställa in alternativet **Skicka inköpsorder via cXML** i inköpsorderrubriken. Dessutom måste inköpsrekvisitionens radtyp för alla rader på inköpsordern vara _extern katalogartikel_. I annat fall kan cXML inköpsordern inte skapas.
- **PUNCHOUTSHIPTO** – om den här egenskapen har värdet _TRUE_ läggs standardadressen för den juridiska personen till i meddelandet om inställning av PunchOut när användaren öppnar en extern katalog. Den här adressen läggs till som **ShipTo**-adress. Leverantörer använder **ShipTo**-adress för att visa prissättning utifrån företagets plats.
- **TRACEPUNCHOUT** – Ange den här egenskapen till _TRUE_ om du får ett felmeddelande när du försöker bläddra till en extern katalog från rekvisitionen. Spårningsinformation fylls sedan i för meddelanden **PunchOutSetupRequest** och **PunchOutResponse** som skickas mellan Supply Chain Management och leverantörens webbplats. Du kan visa den här informationen på sidan **meddelandelogg för cXML-kundvagn** som du kan öppna från sidan **Extern kataloginställning** för den leverantörskatalog som du har problem med. Du bör bara ställa in den här egenskapen på _TRUE_ om du felsöker, eftersom den skapar en stor prestanda i databasen för varje PunchOut. Mer information finns i avsnittet [Vissa meddelandelogg för cXML-kundvagn för extern katalog för PunchOut](#message-log) senare i det här avsnittet.
- **REPLACENEWLINE** – Ange den här egenskapen _TRUE_ om du har problem eftersom en leverantörs system skickar ett **PunchOutResponse**-meddelande som innehåller radinmatningstecken (\\n). Det här problemet kan uppstå om leverantörens meddelanden har parsats mellan mellanprogram eller ett inköpsnav. Om du har problem med en ny leverantörsinställning ställer du in egenskapen **TRACEPUNCHOUT** till _TRUE_ för att visa meddelandet **PunchOutResponse** och bestämma om XML-taggarna är uppdelade efter radinmatningstecken.
- **POCOMMENTS** – Ange den här egenskapen till _TRUE_ om du vill att cXML-dokumentet ska innehålla noteringar som är kopplade till inköpsordern i Supply Chain Management. Den bifogade texten tas med i rubrikkommentarerna i inköpsordermeddelandet. Mer information om hur dessa bifogade filer markeras och bearbetas i systemet finns i [bifoga noteringar till en inköpsorder](#attach-po-notes) senare i det här avsnittet.
- **VENDCOMMENTS** – Ange den här egenskapen till _TRUE_ om du vill att cXML-dokumentet ska innehålla noteringar som är kopplade till inköpsordern i Supply Chain Management. Den bifogade texten tas med i rubrikkommentarerna i inköpsordermeddelandet. Mer information om hur dessa bifogade filer markeras och bearbetas i systemet finns i avsnittet [bifoga noteringar till en inköpsorder](#attach-po-notes).
- **CLEANAMP** – Ange den här egenskapen till _TRUE_ om ett fel meddelande visas när du försöker att göra en PunchOut till en leverantör och leverantörens retur-URL innehåller felaktigt kodade et-tecken (\&).
- **PUNCHOUTTZ** – Ange den här egenskapen till _TRUE_ om den leverantör som du arbetar med använder (Internationella standardiseringsorganisationen) 8601 ISO-standard för att utföra en specifik validering av begärandemeddelandet om PunchOut datum/tid. Supply Chain Management använder datumet Coordinated Universal Time (UTC) i **PunchOutSetupRequest**-meddelandet. Därför när du anger den här egenskapen till _TRUE_, läggs *+00:00* till i formatet datum/tid.
- **WMSADDRESSID** – Ange den här egenskapen till _TRUE_ för att använda lagerställenumret i inköpsorderrubriken som värdet **addressID** i adressen **ShipTo** för den inköpsorderbegäran som skickas till leverantören. Om du anger ett värde för egenskapen **FIXEDSHIPADDRESSID** har det värdet företräde framför detta värde. Därför bör du använda en av egenskaperna eller den andra för att ange värdet **addressID** i addressen **ShipTo** för dokumentet.
- **PUNCHOUTSHIPTOUSER** – den här egenskapen fungerar tillsammans med egenskapen **PUNCHOUTSHIPTO**. Om **PUNCHOUTSHIPTO** anges till _TRUE_ hämtas adressen för den juridiska personen. Om **PUNCHOUTSHIPTOUSER** anges till _TRUE_ används den primära adressen från den användare som använder PunchOut-funktionen istället för adressen till den juridiska personen.

### <a name="activate-the-external-catalog"></a>Aktivera den externa katalogen

När du är klar med att konfigurera alla egenskaper och konfigurera andra inställningar för din externa katalog, gå tillbaka till snabbfliken **Allmänt** för sidan **Externa kataloger** och ange alternativet **Aktiv** till *Ja*.

### <a name="attach-notes-to-a-purchase-order"></a><a name="attach-po-notes"></a>Koppla noteringar till en inköpsorder

Som nämnts i avsnittet [Ange orderegenskaper](#set-order-properties) om du vill att de levererade cXML för att inkludera text från noteringar som är kopplade till relevanta inköpsorder och/eller leverantörsposter, kan du ställa in värdet **POCOMMENTS** och/eller egenskapen **VENDCOMMENTS** till _TRUE_ i den externa katalogen. Det här avsnittet innehåller mer information om hur de här bilagorna markeras och bearbetas i systemet om du använder dem.

Om du vill ange vilka typer av anteckningar som systemet ska söka efter går du till **Anskaffning och källa \> Inställningar \> Formulär \> Formulärinställning**. Sedan på fliken **Inköpsorder** anger du fältet **Inkludera dokument av typen** den typ av notering som du vill kunna ta med. Endast textanteckningar kommer att inkluderas, inte bifogade dokument.

![Inställningssida för formulär.](media/cxml-form-setup.png "Formulär inställningssida")

Bilagor ingår endast i en inköpsorder om deras fält **Typ** anges till värdet du har valt i fältet **Inkludera dokument av typen** och om deras fält **Begränsning** anges till _Extern_. Gå till om du vill skapa, visa eller redigera bilagorna för en inköpsorder **Anskaffning och källa \> Alla inköpsorder**, väljer eller skapar du en inköpsorder och markerar sedan knappen **Bifogade filer** (gemsymbol) i det övre högra hörnet.

![Kopplad anteckning som har konfigurerats att skickas till en leverantör.](media/cxml-note-to-vendor.png "Kopplad notering som har ställts in för att skickas till en leverantör")

## <a name="view-the-cxml-cart-message-log-for-external-catalog-punchout"></a><a name="message-log"></a>Visa meddelandelogg för cXML-kundvagn för extern katalog PunchOut

När du ställer in fältet **PunchOut-protokolltyp** till _cXML_ för en extern katalog, kommer systemet att samla upp en meddelandelogg över de vagnar som kommer tillbaka från leverantörerna. Den här loggen kan användas för felsökning och andra dataändamål.

Om du vill öppna loggen för en extern katalog väljer du relevant katalog och väljer sedan **meddelandelogg för cXML-kundvagn** i åtgärdsfönstret. Sidan **meddelandelogg för cXML-kundvagn** visas en lista över de kundvagnar som har returnerats, den XML som är relaterad till dessa vagnar och de rader som har skapats på den relaterade inköpsrekvisitionen.

![Sida för meddelandelogg för cXML-kundvagn.](media/cxml-cart-message-log.png "Sidan meddelandelogg för cXML-kundvagn")

## <a name="set-the-extrinsic-elements-for-external-catalog-punchout"></a>Ange extrinsic-element för externa katalog PunchOut

När du ställer in fältet **PunchOut-protokolltyp** till *cXML* för en extern katalog kan du lägga till anpassade externa element som kommer att infogas på rätt plats i begäran XML-meddelande.

Om du vill lägga till extrinsic-element i en extern katalog följer du stegen nedan.

1. Gå till **Anskaffning och källa \> Kataloger \> Externa kataloger**.
1. Välj relevant katalog.
1. På snabbfliken **Meddelandeformat** i avsnittet **Extrinsic** välj **Lägg till** för att lägga till en rad i rutnätet för varje yttre element som du vill inkludera. För varje rad anger du följande fält:

    - **Namn** – Ange ett namn för elementet. Det här värdet blir värdet för attributet **namn** för det **Extrinsic** XML-element som skapas av varje rad. Vanligtvis arbetar du med din leverantör för att komma överens med namnet på varje extrinsic-element.
    - **Värde** – Välj ett värde för elementet. Det här värdet blir värdet för XML-element som skapas av varje rad. Följande värden finns:

        - **Användarnamn** – Använd namnet på den användare som gör PunchOut. Det här namnet är inloggningsnamnet för Supply Chain Management.
        - **Användarens e-postadress** – Använd den användarens e-postadress som gör PunchOut. Den här adressen är den adress som användaren har ställt in på fliken **konto** på sidan **användaralternativ**.
        - **Slumpvärde** – Använd ett unikt slumpvärde.
        - **Användarens fullständiga namn** – Ange det fullständiga namnet på den kontaktperson som är kopplad till användaren som använder den externa katalogen.
        - **Förnamn** – Ange förnamnet på den kontaktperson som är kopplad till användaren som använder den externa katalogen.
        - **Efternamn** – Ange efternamnet på den kontaktperson som är kopplad till användaren som använder den externa katalogen.
        - **Telefonnummer** – Ange det primära telefonnumret på den kontaktperson som är kopplad till användaren som använder den externa katalogen.

![Extrinsic-elementinställningar.](media/cxml-extrinsics.png "Extrinsic-elementinställningar")

Användaren eller administratören ser inte extrinsic-elementen eftersom de inte läggs till förrän användaren har en PunchOut. De infogas automatiskt mellan **BuyerCookie** och **BrowserFromPost**-elementen i begärandemeddelandet för cXML-inställning. Därför behöver du inte ställa in dem manuellt i XML-filen när du ställer in den externa katalogen.

![Extrinsic-element har lagts till i XML.](media/cxml-extrinsics-xml.png "Extrinsic-element har lagts till i XML")

## <a name="create-and-process-a-purchase-order"></a><a name="create-po"></a>Skapa och behandla en inköpsorder

När du skapar en inköpsorder för en leverantör ärver den inställningen för alternativet **Skicka inköpsorder via cXML** från leverantören. Inställningen finns emellertid kvar på snabbfliken **Inställningar** i vyn **Rubrik** på inköpsordern, så att du kan ändra den senare efter behov.

![Inköpsorder inställd att använda cXML.](media/cxml-purchase-order.png "Inköpsorder inställd för att använda cXML")

När du skapar en inköpsorder från en inköpsrekvisition som kom från ett PunchOut-flöde fylls all nödvändig radinformation i. Därefter kan du manuellt lägga till inköpsorderrader eller kopiera dem från andra inköpsorder. Var noga med att ange alla obligatoriska fält. Dessa obligatoriska fält innehåller det externa referensnumret, som är det leverantörsnummer som kommer att användas i cXML-meddelandet.

![Exempel på ett externt referensnummer.](media/cxml-line-details.png "Exempel på ett externt referensnummer")

När du har fyllt i all information om inköpsordern måste du bekräfta den. Inget meddelande skickas om inte inköpsordern bekräftas. För att bekräfta en inköpsorder, i åtgärdsfönstret på fliken **Inköp** i gruppen **Åtgärder**, välj **Bekräfta**. 

När inköpsordern har bekräftats kan du visa bekräftelsens status genom journalerna **Bekräftelser av inköpsorder**. I åtgärdsfönstret på fliken **Inköp** i gruppen **Journaler** väljer du **Bekräftelser av inköpsorder**.

Varje inköpsorder kan ha många bekräftelser. Varje bekräftelse markeras med ett inkrementellt nummer. I bilden nedan är inköpsordern *00000275* och bekräftelsen är *00000275-1*. Denna numrering visar standardfunktionen för Supply Chain Management, där ändringar i en inköpsorder och därför vilken typ av cXML-meddelande som ska skickas till leverantören, identifieras utifrån bekräftelsen. Som illustrationen visar innehåller sidan **Bekräftelser av inköpsorder** även fälten **Status för skicka order** och **Leverantörsstatus för orderförfrågan**. För mer information om de olika statusvärdena som du kan se på den här sidan, se avsnittet [Övervaka inköpsorderförfrågningar](#monitor-po-requests) senare i detta avsnittet.

![Bekräftelsesida för inköpsorder.](media/cxml-po-confirmations.png "Sidan bekräftelser av inköpsorder")

Om du vill visa mer information om dokumentet väljer du **begäran om inköpsorder** ovanför rutnätet.

Sidan **Förfrågan om inköpsorder** innehåller två rutnät. Rutnätet i den övre delen av sidan har en post för varje inköpsorder som har markerats för sändning. Rutnätet på fliken **Historik för förfrågan om inköpsorder** i nedre delen av sidan kan ha flera poster för den valda inköpsordern för att ange status för varje bekräftelse. Följande bild visar inköpsorder 00000275 i det övre rutnätet och dokument 00000275-1 i rutnätet på fliken **Historik för förfrågan om inköpsorder**.

![Sidan Förfrågan om inköpsorder.](media/cxml-po-request.png "Sidan förfrågan om inköpsorder")

Om batch-jobbet har ställts in och körs kommer dokumentet att skickas. Du kan visa statusändringen när dokumentet har skickats. I följande bild anges fältet **Status för skicka order** till _Skicka_. Fältet **Leverantörsstatus för orderförfrågan** anges _bekräftad_ för att ange att säljaren fick dokumentet och kunde läsa det och lagra det i sitt system. Rutnätet på fliken **Historik för inköpsorderförfrågan** visar vilken tid dokumentet skickades. För mer information om de olika statusvärdena som du kan se på den här sidan, se avsnittet [Övervaka inköpsorderförfrågningar](#monitor-po-requests).

![Statusmeddelanden på sidan för begäran om inköpsorder.](media/cxml-po-request-2.png "Statusmeddelanden på sidan för begäran om inköpsorder")

## <a name="schedule-the-purchase-order-request-batch-job"></a><a name="po-batch"></a>Tidsplanera batch-jobbet för begäran om inköpsorder

För att aktivera batchjobbet för att skicka inköpsorderförfrågningar, gå till **Anskaffning och källa \> Inställningar \> cXML-hantering \> Förfrågan om inköpsorder** och åtgärdsfönstret på fliken **Förfrågan om inköpsorder** i gruppen **Batch**, välj **Skicka jobb** för att öppna dialogrutan **Inköpsförfrågan förbereda och skicka**. Du kan använda den här dialogrutan när du vill ställa in återkommande intervall, på samma sätt som du vanligtvis använder batch-jobb i Supply Chain Management. Välj ett intervall, baserat på din ordervolym. Även om du kan köra batch-jobbet varje minut är det förmodligen bäst att skicka batchar under hela arbetsdagen, baserat på det orderkvitto som matchar leverantörens scheman.

Leverantören har till exempel en policy som anger att alla order som inlevereras kl. 13:00 kommer att skickas samma dag. I så fall behöver du bara köra batchen några gånger under morgon för att kunna kommunicera alla beställningar som du har. Resten av order kommer sedan att skickas nästa dag. Det här beslutet är ett rent affärsbeslut. Du kan granska den och ställa in parametrarna för det efter detta.

Processen söker efter förfrågningsdokument för inköpsorder med statusen *väntar*. Om du har en order som du måste skicka direkt till en leverantör kan du välja **Skicka jobb** och ange alternativet **Batchbearbetning** till *Nej*.

## <a name="monitor-purchase-order-requests"></a><a name="monitor-po-requests"></a>Övervaka inköpsorderförfrågningar

### <a name="view-the-status-of-a-purchase-order"></a>Visa statusen för inköpsordern

När order som kan skickas via cXML bekräftas hamnar de i statusen _väntar_. Som beskrivs i avsnittet [Skapa och bearbeta en inköpsorder](#create-po) kan du visa inköpsorderns status på sidan för **Förfrågan om inköpsorder**. Varje begäran om inköpsorder kan ha en av flera statusvärden, beroende på dess parametrar och data. I det här avsnittet beskrivs olika statustyper och vilka värden de kan ha. Den här informationen kan hjälpa dig att hantera ärenden och förstå statusen på dina inköpsorder.

![Inköpsorderstatus på sidan för begäran om inköpsorder.](media/cxml-monitor-po-request.png "Inköpsorderstatus på sidan för begäran om inköpsorder")

Rutnätet i den övre delen av sidan **Förfrågan om inköpsorder** kan visa följande statusvärden:

- **Status för skicka order** – Det här fältet kan ha ett av följande värden:

    - **Väntar** – dokumentet väntar på att skickas.
    - **Skickat** – dokumentet har skickats.
    - **Stoppat** – dokumentet markerades som _stoppat_ innan det skickades. (För att markera ett dokument som _Stoppat_ väljer du **stoppa** i åtgärdsfönstret på sidan **Inköpsförfrågan**.)
    - **Arkiv** – dokumentet har rensats. (För att rensa ett dokument som du **Rensa** i åtgärdsfönstret på sidan **Inköpsförfrågan**.)

- **Leverantörsstatus för orderförfrågan** – Det här fältet kan ha ett av följande värden:

    - **Väntar** – dokumentet väntar på att skickas.
    - **Bekräftad** – dokumentet har bekräftats som inlevererat av leverantören. Du kan granska det detaljerade XML-meddelande som returneras från leverantören genom att välja fliken **Svars-XML** på sidans nedre del.
    - **Fel** – dokumentet skickades till leverantören, men ett fel uppstod. Du kan granska felmeddelandet genom att välja fliken **Svars-XML** för svar på sidans nedre del.

Rutnätet på fliken **Historik för inköpsorderförfrågan** i den nedre delen av sidan **Förfrågan om inköpsorder** kan innehålla följande värden:

- **Typ av orderförfrågan** – Det här fältet kan ha ett av följande värden:

    - **Ny** – raden markeras som ny omedelbart efter det att inköpsordern har bekräftats.
    - **Uppdatera** – om en bekräftelse redan har skickats och bekräftats av leverantören kommer nästa bekräftelse att markeras som _uppdatering_. Uppdateringar kommer endast att skickas om alternativet **Skicka uppdateringar för inköpsförfrågningar** är inställt på *Ja* i de [globala cXML-parametrarna](#cxml-parameters).
    - **Ta bort** – om en bekräftelse redan har skickats och bekräftats av leverantören, men inköpsordern annulleras, markeras den bekräftelse som väntar på att _tas bort_. Borttagningar kommer endast att skickas om alternativet **Skicka borttagningar för inköpsförfrågningar** är inställt på *Ja* i de [globala cXML-parametrarna](#cxml-parameters).

- **Tid för begäran** – den tidpunkt då orderbekräftelsen skapades. Du kan jämföra tiden för begäran med orderstatustiden för att fastställa tiden mellan bekräftelse och leverantörsbekräftelsen.
- **Status för skicka order** – det här fältet är samma som i fältet **Status för skicka order** i den övre delen av sidan. Det upprepas här för att göra det enklare att se status på bekräftelsenivå. Om fältet **Typ av orderförfrågan** anges till *Ny* och inköpsordern bekräftas på nytt innan en bekräftelse skickas, fältet **Status för skicka order** anges till *Arkiv*.
- **Orderstatustid** – den tidpunkt då posten för historik för inköpsorderförfrågan senast uppdaterades. (Uppdateringarna inkluderar statusändringar.)
- **Leverantörsstatus för orderförfrågan** – det här fältet är samma som i fältet **Leverantörsstatus för orderförfrågan** i den övre delen av sidan. Det upprepas här för att göra det enklare att se status på bekräftelsenivå.
- **Tid för skicka vidare** – den tidpunkt då posten skickades igen.
- **Antal skicka vidare** – Antalet gånger som posten har skickats in på nytt. Ett högt värde anger flera fel och kan därför tyda på ett problem med en av datainställningarna eller leverantörens datainställning.

### <a name="view-the-xml-for-a-purchase-order-request-message"></a>Visa XML-koden för ett meddelande inköpsorderförfrågan

Om du vill visa XML för meddelande om inköpsorderförfrågan, välj fliken **Begär XML-text** på sidan för **inköpsorderförfrågan**. Informationen på den här fliken kan vara till hjälp vid testning eller felvalidering. För att informationen ska bli lättare att läsa kan du visa den som ett formaterat meddelande. Kopiera innehållet på fliken till en textfil och visa den i en XML-redigerare.

![Fliken Begär XML-text.](media/cxml-request-xml-text.png "Fliken begär XML-text")

### <a name="view-the-details-of-the-vendor-response"></a>Visa mer information om leverantörens svar

Om du vill visa innehållet i en leverantörsbekräftelse eller ett fel svar väljer du fliken **svars-XML** längst ned på sidan **Förfrågan om inköpsorder**.

![Fliken XML-svar.](media/cxml-response-xml.png "Fliken svars-XML")

## <a name="additional-resources"></a>Ytterligare resurser

- [Ställ in en extern katalog för PunchOut eProcurement](set-up-external-catalog-for-punchout.md)
- [Använd externa kataloger för PunchOut eProcurement](use-external-catalogs-for-punchout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
