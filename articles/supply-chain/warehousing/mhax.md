---
title: Materialhanteringsutrustningens gränssnitt (MHAX)
description: I denna artikel beskrivs hur du konfigurerar materialhanteringsutrustningens gränssnitt (MHAX) så att du kan ansluta till externa system för fysisk materialhantering (MH).
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMHEParameters, WMHESubscription, WMHEQueueManagerWorkspace, WMHEInboundQueue, WMHEOutboundQueue
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 1056c7aee3ea96ddcb012704be40bef6c363f323
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334368"
---
# <a name="material-handling-equipment-interface-mhax"></a>Materialhanteringsutrustningens gränssnitt (MHAX)

[!include [banner](../../includes/banner.md)]

Du kan använda *utrustningsgränssnittet för materialhantering* (MHAX) för att ansluta externa fysiska materialhanteringssystem (MH) till ett lager som hanteras av lagerstyrningsprocesser (WMS) i Microsoft Dynamics 365 Supply Chain Management. Gränssnittet mellan WMS- och MJ-systemen består av två köer: en för utgående händelser (WMS till MH) och en för inkommande händelser (MH till WMS). WMS-systemet genererar utgående händelser baserade på arbetsrader som skapas under olika arbetsskapande- och körningsprocesser. MH-systemet söker sedan regelbundet i WMS-systemet efter nya händelser och bearbetar svaren. När MH-systemet har slutfört hanteringen av händelserna i enlighet med arbetsinstruktioner skickar det inkommande händelser, till exempel slutförande av arbetsrad och kort plockning.

I följande bild visas de olika elementen och ordningen som processer uppstår i när du använder MHAX-integrering.

![MHAX-komponenter och -interaktioner.](media/mhax-components.png "MHAX-komponenter och interaktioner")

Här är en förklaring av de interaktioner som visas i föregående illustration:

1. När du skapar jobb eller arbete skapas utgående händelser i den utgående kön.
2. MH-utrustning ansluter till MH-utrustningstjänsten, söker efter nya händelser som är relevanta för den och bearbetar dessa händelser.
3. När MH-utrustning är klar att rapportera tillbaka ansluts den till tjänsten igen och skickar inkommande händelser. Dessa händelser bearbetas omedelbart av köprocessorn.
4. Baserat på de inkommande händelsedata kan köprocessorn köra befintligt arbete, ändra det eller skapa nytt arbete.

## <a name="turn-on-the-mhax-feature"></a>Aktivera MHAX-funktion

Innan du kan använda MHAX-funktionen måste du aktivera både dess funktion och dess konfigurationsnyckel.

1. Om du kör Supply Chain Management version 10.0.28 eller tidigare, gör följande:
    1. Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.
    1. I arbetsytan **[Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** aktivera funktionen som heter *Materialhanteringsutrustningens gränssnitt*. (Från och med version 10.0.29 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras.)
1. Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
1. Expandera **Handel \> Hantering av lager och transport** och markera sedan kryssrutan **Materialhanteringsutrustningens gränssnitt**.
1. Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

## <a name="set-mhax-parameters"></a>Ställa in MHAX-parametrar

Du måste konfigurera några allmänna parametrar på sidan **Parametrar för materialhanteringsutrustningens gränssnitt** för att konfigurera funktionen.

1. Gå till **Materialhanteringsutrustningens gränssnitt \> Inställningar \> Parametrar för materialhanteringsutrustningens gränssnitt**.
2. Ange följande fält på fliken **Allmänt**:

    - **Användar-ID** – Välj en arbetare. Den här arbetaren kommer att användas för att köra alla arbetsåtgärder (plocka och placera) som bearbetas via den inkommande kön.
    - **Aktivera inkommande meddelande-ID** – När det här alternativet är inställt *Ja*, om ett dubbelt inkommande meddelande-ID mottas kommer meddelandet att avvisas och ett felmeddelande anger att meddelandet redan finns. När det här alternativet ställs in på *Nej*, tillåts dubbletter av inkommande meddelanden.

3. På fliken **Nummerserier** väljer du de systemövergripande nummerserier som ska användas för att generera unika ID:ar för inkommande köartiklar, utgående köartiklar och arbetsradpar.

## <a name="outbound-events"></a>Utgående händelser

Vid specifika punkter under skapandet av arbetet eller utförandet avgör systemet om det måste generera utgående händelser att skicka till MH-systemet. Om ett abonnemang har konfigurerats för en viss punkt under bearbetningen av lagerstället genererar systemet händelsen enligt inställningarna för abonnemanget.

### <a name="structure-of-outbound-events"></a>Struktur för utgående händelser

Varje utgående händelse identifieras unikt av ett utgående kö-ID. Typen av utgående transaktion avgör händelsens typ. Lagerstället och ID:t för abonnemanget som genererade händelsen registreras också på händelsen.

Om du vill föra data till MH-systemet innehåller den utgående händelsen 10 fält för data (**data01** till **data10**). Dessa datafält har en till en-mappning (1:1) till befintliga databasfält. De extraheras specifikt från fält i arbetsraden och arbetshuvudregister. Fälten kan väljas fritt. Du konfigurerar dem när du skapar abonnemanget.

Förutom de 10 datafält som har en 1:1-mappning till befintliga databasfält kan händelsen innehålla ett ytterligare datafält som kallas för *nyttolast*. Innehållet i det här fältet genereras av en anpassad X++-kod som kallas för *nyttolastgenerator*. Alla nyttolastgeneratorer som ska användas ställs in i abonnemanget.

Om du vill säkerställa att MH-systemet bara tar emot varje utgående kö-ID en gång, används ett statusfält för att ange om en händelse är klar att skickas till det externa systemet eller om den redan har skickats.

### <a name="outbound-queue-subscriptions"></a>Utgående köabonnemang

Innan händelser genereras måste ett abonnemang ställas in för att ange om MHAX-funktionen ska genereras och om den ska genereras. Genererade händelser märkas med abonnemangs-ID:t. Därför kan flera MH-system ansluta till samma WMS-system men hålla sina händelser åtskilda. När MHAX-tjänsten söker efter nya händelser är ett abonnemang ett av de tillgängliga alternativen när du hämtar händelserna.

Om du vill skapa ett abonnemang går du till **Materialhanteringsutrustningens gränssnitt \> Inställningar \> Abonnemang**. För varje abonnemang är följande parametrar tillgängliga:

- **Abonnemangs-ID** – Ett unikt namn som identifierar abonnemanget.
- **Beskrivning** – En fritextbeskrivning av prenumerationen.
- **Lagerställe** – De specifika lagerställen som händelser ska filtreras efter.
- **Utgående transaktionstyp** – Den typ av händelser som abonnemanget ska innehålla.
- **Nyttolastgenerator** – Ett valfritt kodtillägg som kan ange ytterligare information i fältet **Nyttolast** i den utgående händelsen.

En fråga kan kopplas till varje abonnemang. Den här frågan filtrerar arbetsrader och huvuden för att ytterligare begränsa det arbete som kommer att använda abonnemanget för att generera händelser. Om du vill lägga till en fråga till ett abonnemang markerar du kryssrutan **Kör fråga** för relevant abonnemang på sidan **Abonnemang** och väljer sedan **Redigera fråga** i åtgärdsfönstret. Frågeredigeraren för standard Supply Chain Management.

Dessutom innehåller abonnemanget en *abonnemangsmappning* som mappar fält från arbetshuvudet eller arbetsraden till några av eller alla de 10 kostnadsfria datafälten i den utgående händelsen, efter behov. Om du vill returnera information till MHAX-tjänsten inkluderar du vanligtvis arbetsradspost-ID eller *arbetsradpar-ID*. (Arbetsradpar-ID är en ny egenskap som gör det möjligt för systemet att använda ett enda returkommando för bearbetning av plock- och inleveransrader.) Återstående fält beror på användningsfallen. Det finns några exempel längre fram i denna artikel.

Om du vill konfigurera en abonnemangskarta väljer du relevant abonnemang på sidan **Abonnemang** och väljer sedan **Abonnemangsmappning** i åtgärdsfönstret. I dialogrutan **abonnemangsmappning** som visas kan du tilldela ett register och ett fält för varje tillgängligt datafält när det behövs.

### <a name="outbound-event-types"></a>Utgående händelsetyper

Det här avsnittet beskriver olika typer av händelser som är tillgängliga. (Händelsetyper kallas också för *transaktionstyper*.) Det förklarar också när varje typ av händelse skapas i WMS-systemet.

#### <a name="work-creation-events"></a>Händelser för att skapa arbete

Händelser för att skapa arbete skapas efter att arbetet har genererats av programmet. Detta beteende gäller för de flesta typer av processer för att skapa arbete, oftast när det gäller att skapa plocknings- och påfyllnadsarbete. Om arbete i allmänhet skapas i ett *öppet* tillstånd, vilket innebär att arbetet är klart att köras av en arbetare, genereras en händelse för att skapa arbetet. Dessutom skapas händelser för skapande av arbete för grundläggande rörelsearbete (inte förflyttningar per mallarbete), även om arbetet inte har skapats som öppet arbete.

Ett undantag till detta är att du arbetar med arbetsuppgift för rullande inventering, som för närvarande inte stöds. Lagerinventering i MH-systemet ligger utanför MHAX-området och resultatet av inventeringar måste importeras till en lagerinventeringsjournal.

När arbetet har skapats bearbetar MHAX-tjänsten de arbetsrader som skapas och tilldelar ett arbetsradpar-ID till alla genererade arbetsrader för varje arbetsrubrik. Målet är att gruppera alla plockarbetesrader med de på varandra följande under ett arbetsradspar-ID. (Grupperna motsvarar plock-/placeringspar i arbetsmallar.) På det här sättet kan ett enskilt ID användas för att rapportera slutförande av arbete för alla relaterade plocknings- och placeringsrader. Grupperingsprocessen startar med den första raden och fortsätter sedan med samma ID tills den stöter på ett efterföljande par placering-/plockarbetsrader. Det löpande ID:t tilldelas placeringsrad för det paret. Ett nytt ID som sedan används för plockraden för paren vidare. Den här processen fortsätter tills alla rader som tillhör arbetsrubriken har bearbetats.

Som en särskild funktion för händelser för att skapa arbete om alternativet **Spärrad påfyllnad** anges till *Ja* i arbetsrubriken har händelserna som genereras status *Spärrad* istället för den vanliga statusen för *Klar* som används för att skicka dem till MH-systemet. Flaggan **Spärrad påfyllnad** i arbetsrubriken indikerar att arbetsrubriken ännu inte är klar för arbetare som ska köras, kanske på grund av att påfyllnaden inte är klar. När flaggan **Spärrad påfyllnad** är avmarkerad tas händelser som redan skapats bort och är tillgängliga för MH-systemet att hämta från kön.

#### <a name="work-initiation-events"></a>Händelser för att initiera arbete

Händelser med arbetstillstånd utlöses när arbetsstatusen ändras från *Öppen* till *Pågår* under arbetsuppdateringen.

#### <a name="work-completion-events"></a>Händelser för att slutföra arbete

Händelser med arbetstillstånd utlöses när arbetsstatusen ändras från *Öppen* till *Pågår* under arbetsuppdateringen.

#### <a name="work-cancellation-events"></a>Händelser för annullera arbete

Händelser för annullera arbete utlöses när arbetsstatusen ändras från någon status förutom *Annullerad* till *Annullerad* under arbetsuppdateringen. Alla andra händelser som är relaterade till arbetsrubriken tas dessutom bort från kön för alla abonnemang. På det här sättet förhindras externa system från att bearbeta händelser som inte behövs.

#### <a name="pickput-completion-events"></a>Händelser för plocka/placera slutförande

Händelser för plocka/placera slutförande utlöses när placering-/plockarbetsrader ändras från *Öppen* till *Pågår* under arbetsraduppdateringen.

### <a name="monitor-the-outbound-queue"></a>Övervaka den utgående kön

Du granskar din utgående kö genom att gå till **Materialhanteringsutrustningens gränssnitt \> Vanlig \> Utgående köer**. Sidan **Utgående kö** anger varje utgående köartikel och dess status. Markera en köartikel om du vill visa information om den. Dessa detaljer inkluderar artikelns transaktionstyp, abonnemanget som den användes och värden för varje datafält (**data01** till **data10**) och nyttolast.

### <a name="clean-up-the-outbound-queue"></a>Rensa upp den utgående kön

Så småningom börjar din utgående kö bli full av köartiklar som redan har skickats. Om du vill ta bort dessa artiklar går **Materialhanteringsutrustningens gränssnitt \> Periodiska uppgifter \> Rensa \> Rensa den utgående kön**.

## <a name="inbound-events"></a>Ingående händelser

Det här avsnittet beskriver olika typer av inkommande händelser som MH-systemet kan rapportera tillbaka till WMS-systemet. Det förklarar också data måste levereras av MH-systemet, och vad varje inkommande händelse gör i WMS-systemet.

### <a name="structure-of-inbound-events"></a>Struktur för ingående händelser

När en inkommande händelse skickas måste det externa systemet tillhandahålla den inkommande transaktionstypen tillsammans med upp till 10 parametrar (**data01** till **data10**). Valfri validering kan säkerställa att MHAX-tjänsten inte har fått samma inkommande händelse mer än en gång. För att denna validering ska kunna aktiveras måste varje inkommande händelse ha ett unikt meddelande-ID. Om ett dubblettmeddelande-ID tas emot och alternativet **Aktivera inkommande meddelande-ID** anges till *Ja* på sidan **Parametrar för materialhanteringsutrustningens gränssnitt** kommer meddelandet avvisas. Ett felmeddelande visar att meddelandet redan finns.

Förutom fält för inkommande data tilldelar systemet ett unikt inkommande kö-ID till händelsen.

### <a name="inbound-event-types"></a>Ingående händelsetyper

Det här avsnittet beskriver de inkommande händelsetyper (transaktionstyper) som stöds och de data som måste anges för att händelser ska kunna bearbetas.

#### <a name="work-confirm-events"></a>Händelser för arbetsbekräftelse

Händelser för arbetsbekräftelse kräver att inkommande datafält innehåller följande information:

- **data01** – Arbetsradpar-ID.
- **data02** – Post-ID för arbetsraden (`RecId` värde).

    > [!NOTE]
    > *Antingen* fältet **data01** *eller* måste fältet **data02** finnas med.

- **data03** – Nummer-ID som ska plockas.
- **data04** – Arbetsrubrikens målnummer-ID.

Om ID för arbetsradspar tillhandahålls, markeras alla plocknings-, placerings- eller anpassade arbetsrader som är markerade med ID för arbetsradspar och som har statusen *Öppna* eller *Pågår*, körs efter varandra. Om ett post-ID för arbetsraden (`RecId` värde) tillhandahålls måste arbetslinjen vara en plocka, placera eller anpassad arbetsrad som har statusen *Öppna* eller *Pågår*.

Välj rader från nummerplatskontrollerade platser kräver att **data03** ange ID-numret som ska plockas från, oavsett om raderna är markerade med arbetsradens post-ID eller arbetsradens par-ID. Fältet **data04** måste ange arbetshuvudets ID-nummer för valet.

Placeringsrader accepterar inte mer information. De körs endast baserat på den aktuella arbetsradens plats och arbetets målnummer-ID. Om placeringen måste göras till en annan plats, ändra då arbetsradens plats enligt beskrivningen i avsnittet [Åsidosätt händelser](#override-events) senare i denna artikel.

Anpassade arbetsrader behöver inte, eller stöder, någon ytterligare information i den inkommande händelsen.

#### <a name="short-pick-events"></a>Korta plockhändelser

Korta plockhändelser kräver att inkommande datafält innehåller följande information:

- **data02** – Arbetspost-ID (`RecId` värde).
- **data03** – Nummer-ID som ska plockas.
- **data04** – Kvantiteten som ska plockas.
- **data05** – den undantagskoden för kort plockning.
- **data06** – Arbetsrubrikens målnummer-ID.

> [!NOTE]
> Fältet **data01** används inte för korta plockhändelser.

Den här händelsen liknar händelser för arbetsbekräftelse, men den gäller endast för plockrader.

#### <a name="override-events"></a><a id="override-events"></a>Åsidosätt händelser

Åsidosätt händelser kräver att inkommande datafält innehåller följande information:

- **data01** – Arbetspost-ID (`RecId` värde).
- **data02** – Det nya plats-ID:t.

Arbetsraden måste ha statusen *Öppen* eller *Pågår* och den nya platsen måste finnas.

#### <a name="license-plate-receipt-events"></a>Inleveranshändelser för ID-nummer

Inleveranshändelser för ID-nummer kräver att inkommande datafält innehåller följande information:

- **data01** – ID för det inkommande ID-nummer som ska inlevereras.

Systemet utför en Inleveransåtgärd för ID-nummer, baserat på ID-numret som skickas in som fältets värde **data01**.

### <a name="monitor-the-inbound-queue"></a>Övervaka den ingående kön

Du granskar din ingående kö genom att gå till **Materialhanteringsutrustningens gränssnitt \> Vanlig \> Ingående köer**. Sidan **Ingående kö** anger varje ingående köartikel och dess status. Markera en köartikel om du vill visa information om den. Dessa detaljer inkluderar artikelns transaktionstyp, meddelande-ID och värden för varje datafält (**data01** till **data10**).

Om ett fel eller någon annan typ av loggartikel uppstod när inkommande händelser bearbetades, kan du kontrollera loggen genom att välja **Fellogg** i åtgärdsfönstret.

### <a name="inbound-event-processing"></a>Inkommande händelsebearbetning

Inkommande händelser skrivs först till databasen och de körs sedan omedelbart (synkront) . Om ett fel inträffar under bearbetningen skrivs händelsen fortfarande till kön, men status ställs in på *Felaktigt*. MHAX-tjänsten returnerar ett felmeddelande till MH-systemet och lagrar felloggen i den inkommande händelseposten för senare undersökningar.

Händelser med statusen *felaktig* bearbetas på nytt senare om felvillkoret är fast. Gör så här om du vill bearbeta dem igen:

- Gå till **Materialhanteringsutrustningens gränssnitt \> Vanlig \> Ingående köer**. Markera relevant kö för inkommande meddelanden och välj **Bearbeta igen** i åtgärdsfönstret.
- Gå till **Materialhanteringsutrustningens gränssnitt \> Vanlig \> Bearbeta felaktig inkommande kö igen**. En dialogruta för standard batchjobb visas. Där kan du konfigurera ett postfilter och schemalägga eller köra ett batchjobb för att bearbeta kön på nytt.

Alla arbetsåtgärder (plock och puts) körs med hjälp av arbetaren som valts i fältet **Användar-ID** på sidan för **Parametrar för materialhanteringsutrustningens gränssnitt**.

### <a name="clean-up-the-inbound-queue"></a>Rensa upp den ingående kön

Så småningom börjar din ingående kö bli full av köartiklar som redan har bearbetats. Om du vill ta bort dessa artiklar går **Materialhanteringsutrustningens gränssnitt \> Periodiska uppgifter \> Rensa \> Rensa den ingående kön**.

## <a name="get-a-quick-overview-by-using-the-queue-manager"></a>Få en snabb överblick med köhanteraren

För att få en snabb översikt över all aktivitet som är relaterad till dina inkommande och utgående köer, gå till **Materialhanteringsutrustningens gränssnitt \> Arbetsytor \> Köhanterare**. På sidan **Köhanteraren** finns en uppsättning flikar som du kan använda för att övervaka och utforska köerna. Den innehåller även användbara länkar till de flesta andra sidor som nämns i denna artikel.

## <a name="connect-to-the-mhax-service"></a>Ansluta MHAX-tjänster

MHAX är implementerat som en anpassad tjänst. Därför är det tillgängligt via SOAP- och REST-samtal. Här finns adresserna för SOAP- och REST-slutpunkterna:

- **SOAP:** `https://base_environment_URL/soap/services/WMHEServices`
- **REST:** `https://base_environment_URL/api/services/WMHEServices/WMHEService`

## <a name="retrieve-messages-from-the-outbound-queue"></a>Hämta meddelanden från den utgående kön

Om du vill hämta meddelanden från den utgående kön använder du någon av följande metoder:

- Använd `readOutboundSubscriptionQueue` när du vill hämta händelser baserade på abonnemangs-ID:t.
- Använd `readOutboundWarehouseQueue` när du vill hämta händelser baserat på händelsetypen och lagerställe-ID för flera abonnemang.
