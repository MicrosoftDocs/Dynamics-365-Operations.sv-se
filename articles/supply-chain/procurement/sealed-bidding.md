---
title: Sluten budgivning för anbudsförfrågningar
description: I det här avsnittet beskrivs hur du ställer in stängd budgivning så att leverantörsbud är stängda tills de öppnas av inköpspersonal.
author: GalynaFedorova
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: dfc19646d6724627c8a25bcfc8a6b2a70a73c261
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675161"
---
# <a name="sealed-bidding-for-rfqs"></a>Sluten budgivning för anbudsförfrågningar

[!include [banner](../includes/banner.md)]

Stängd budgivning håller leverantörsbud stängda tills de öppnas av inköpspersonal. Alla bud som är relaterade till en anbudsförfrågan är först tillgängliga och kan inte läggas till vid utgångna bud. Innan ett anbud öppnas har bara användare med dedikerade användarroller och som representerar leverantören åtkomst till det.

> [!IMPORTANT]
> Ändring eller utökande formulär eller skapande av nya formulär eller affärslogik kan skydda det skydd som Microsoft tillhandahåller för att skydda miljön. Du bär risken att använda några ändringar, tillägg, nya formulär eller affärslogik, eller oförmåga att använda den stängda budgivningsfunktionen på grund av sådana ändringar, tillägg, nya formulär eller affärslogik.  Microsoft ansvarar inte för någon sådan skada som uppstår vid ändringar eller tillägg av formulär, eller eventuella nya formulär eller affärslogik som du skapar, eller som någon utomstående part skapar åt dig. Microsoft tillhandahåller inte teknisk eller annat stöd för ändringar, tillägg, nya formulär eller affärslogik som du eller någon tredje part har gjort på uppdrag av dig. Du är ensam ansvarig för att följa alla tillämpliga lagar eller förordningar angående stängd budgivning.

## <a name="how-bids-are-kept-secure"></a>Så hålls anbud stängda

Stängd budgivning använder asymmetrisk kryptering för att kryptera anbudets krypteringsnyckeln (KEK) och symmetrisk kryptering för att kryptera det faktiska anbudet. Systemet integreras med Microsoft Azure Key Vault för att generera och hantera de krypteringsnycklar som används för att kryptera stängda anbud. Varje anbud har sin egen krypteringsnyckel. Krypteringen förvaras i ett nyckelvalv som ägs av organisationen som kör Dynamics 365 Supply Chain Management. Systemet kommer åt nyckelvalvet vid behov när kryptering och dekryptering krävs.

## <a name="setup-and-configuration"></a>Installation och konfiguration

I det här avsnittet beskrivs de krav som måste uppfyllas för att du ska kunna skicka ut anbudsförfrågan som kräver stängd budgivning.

### <a name="step-1-set-up-user-access-to-sealed-bidding"></a>Steg 1: Ställa in användaråtkomst för stängd budgivning

När du använder stängd budgivning kan bara användare som är inställda som kontaktperson för en leverantör visa, redigera och lämna anbud för leverantören tills anbudstiden är slut. Dessa användare måste ha rollen **Leverantör (extern)** och de måste anges som kontaktperson för leverantörskontot. Kontaktpersonen måste också ha behörighet att samarbeta med leverantörer, så som beskrivs i [Ställa in och underhålla leverantörssamarbete](set-up-maintain-vendor-collaboration.md).

Eftersom användare med rätt behörighet och som har ställts in som leverantörskontakter kan komma åt de stängda anbuden för en leverantör, är det viktigt att spåra vilka dessa användare är. Systemadministratören som ställer in användare och säkerhetsroller ansvarar för att begränsa åtkomst till stängda anbud till de användare som verkligen tillåts visa dem.

### <a name="step-2-enable-the-sealed-bidding-feature"></a>Steg 2: Aktivera funktionen för stängd budgivning

Innan du börjar ställa in eller använda funktionen måste du se till att den är tillgänglig i ditt system. Administratörer kan använda arbetsytan **[Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** för att kontrollera funktionens status och aktivera den vid behov. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *anskaffning och källa*
- **Namn på funktion:** *Stängd budgivning för anbudsförfrågan*

### <a name="step-3-set-up-azure-key-vault"></a>Steg 3: Konfigurera Azure Key Vault

Supply Chain Management använder krypteringsnycklar för att skydda alla stängda anbud och hålla dem stängda till lämplig tidpunkt. Det utnyttjar möjligheten att i Key Vault att generera och hantera nödvändiga nycklar. Därför måste du ställa in en anslutning från Supply Chain Management till ett nyckelvalv som aktiverar systemet.

> [!IMPORTANT]
> De nyckelvalv som du använder för att uppfylla dessa villkor måste uppfylla följande krav:
>
> - Om du använder en säkerhetsnyckel för utveckling och testning måste du ha ett dedikerat nyckelvalv för produktionen och ett separat för produktion.
> - Varje nyckelvalv måste skapas i ett Azure-abonnemang som ägs av din organisation (inte det abonnemang där du kör Supply Chain Management).
> - Varje nyckelvalv måste bara användas för stängd budgivning. Du får inte använda dina nyckelvalv med stängd budgivning för något annat syfte.

Varje anbud hämtar sin egen hemliga nyckel. Nyckeln används varje gång en användare visar, uppdaterar eller öppnar anbudet.

Key Vault genererar nyckeln som används för att hämta hemligheten när leverantören väljer **Anbud** i leverantörens samarbetsgränssnitt. Nyckeln upphör sedan att gälla efter en fastställd tid som inköpschefen anger på sidan **Parametrar för anskaffning och sourcing** i Supply Chain Management. När nyckeln har upphört att gälla kan ingen visa, redigera eller öppna budet. Därför är det viktigt att konfigurera nyckelns utgång så att det finns tillräckligt med tid för att processen ska kunna slutföras.

I de följande tre stegen ställer du in anslutning till Key Vault. Först ska du ställa in ett nyckelvalv som ska användas för stängd budgivning. Sedan ska du konfigurera Supply Chain Management att kommunicera med nyckelvalvet. Slutligen ställer du in utgångstid för nyckeln.

### <a name="step-4-set-up-a-key-vault-to-use-with-sealed-bidding"></a>Steg 4: Ställ in ett nyckelvalv som ska användas för stängd budgivning

Följ dessa steg för att ställa in nyckelvalvet. Stegens ordningsföljd är mycket viktig.

1. Om du inte redan har ställt in ett Azure-abonnemang som är separat från abonnemanget där du kör Supply Chain Management ställer du in det.
1. Ställa in ett nyckelvalv i ett separat Azure-lagringsutrymme. Mer information finns i [Underhålla Azure Key Vault lagringsutrymme](https://support.microsoft.com/help/4040294/maintaining-azure-key-vault-storage).
1. Ställ in ditt Supply Chain Management-program så att det fungerar som en klient för nyckelvalvet. Mer information finns i [Konfigurera Azure Key Vault-klienten](https://support.microsoft.com/help/4040305/setting-up-azure-key-vault-client).

### <a name="step-5-configure-key-vault-parameters-in-supply-chain-management"></a>Steg 5: Konfigurera parametrar för Key Vault i Supply Chain Management

Följ de här stegen för att konfigurera Supply Chain Management att kommunicera med nyckelvavet under stängd budgivning.

1. Logga in i Supply Chain Management och gå till **Parametrar för systemadministration \> Inställning \> Parametrar för Key Vault**.
1. Välj **Ny** för att skapa en post och ställ in följande fält för den:

    - **Namn** – Ange ett namn.
    - **Beskrivning** – Ange en beskrivning.
    - **URL för Key Vault** – Ange standard-URL för ditt nyckelvalv.
    - **Key Vault-klient** – Ange interaktivt klient-ID för Active Directory-programmet som är associerat till ett nyckelvalv för autentisering.
    - **Hemlig Key Vault-nyckel** – Ange hemlig referens för certifikatet.
    - **Aktiverat för stängd budgivning** – Ange alternativet som *Ja*.

![Sida med parametrar för Key Vault](media/sealed-bidding-key-vault-param.png "Sida med parametrar för Key Vault")

> [!NOTE]
> Du kan bara aktivera en nyckelvalvskonfiguration för stängd bugivning åt gången. Innan du inaktiverar en befintlig nyckelvalvskonfiguration måste du se till att alla stängda anbud som använder den har öppnats. Granska alla anbudsförfrågningar av typen *Stängda* aoch se till att alla anbud är öppnade.

### <a name="step-6-set-the-key-expiration-time"></a>Steg 6: Ange nyckelns utgångstid

Ställ in utgångstiden som används för nyckeln som genereras för varje nytt anbud genom att följa stegen nedan.

1. Gå till **Parametrar för anskaffning och sourcing \> Inställningar \> Parametrar för anskaffning och sourcing**.
1. Ange i fältet **Dagsförskjutning** det antal dagar som anbudsförfrågan ska pågå på fliken **Anbudsförfrågan**. När en anbudsförfrågan skapas läggs antal dagar som du anger här till systemets datum för att definiera standard utgångsdatum för anbudsförfrågan.
1. I fältet **Förskjutning för krypteringsnyckel utgångsdatum** anger du antal dagar som varje krypteringsnyckel ska vara giltig när den har utfärdats. När krypteringsnyckeln har upphört att gälla kan ingen visa, redigera eller öppna det stängda anbud som använder den.

> [!TIP]
> Värdet i fältet **Förskjutning för krypteringsnyckel utgångsdatum** får inte vara lägre än värdet i fältet **Dagars förskjutning**.

### <a name="step-7-set-the-default-bid-type"></a><a name="set-default-bid-type"></a>Steg 7: Ställ in standard anbudstyp

Alla anbudsförfrågningar har en anbudstyp. Anbudstypen anger om anbudsförfrågan är öppen eller stängd budgivning.

#### <a name="rfq-cases-that-dont-have-a-solicitation-type"></a>Anbudsförfrågansärenden som inte har någon förfråganstyp

Ställ in standard för anbudstyp som tilldelas nya anbudsförfrågningar som inte tilldelas någon förfråganstyp när de skapas genom att följa stegen nedan.

1. Gå till **Parametrar för anskaffning och sourcing \> Inställningar \> Parametrar för anskaffning och sourcing**.
1. På fliken **Anbudsförfrågan** ställer du in fältet **Anbudstyp** som *Stängd*.

#### <a name="rfq-cases-that-have-a-solicitation-type"></a>Anbudsförfrågansärenden som har förfråganstyp

Ställ in standard för anbudstyp som tilldelas nya anbudsförfrågningar som tilldelas förfråganstyp när de skapas genom att följa stegen nedan.

1. Gå till **Anskaffning och sourcing \> Inställning \> Anbudsförfrågan \> Förfråganstyp**.
1. Skapa en ny förfråganstyp eller välj en befintlig förfråganstyp där du vill använda anbudstypen *Stängd*.
1. Ställ in fältet **Anbudstyp** på *Stängd*.
1. Upprepa de här stegen för varje ytterligare förfråganstyp där du vill implementera stängd budgivning.

> [!TIP]
> En förfråganstyp behöver inte tilldelas när en ny anbudsförfrågan skapas. Om en förfråganstyp har tilldelats kan standard anbudstyp för en anbudsförfrågan hämta den. Annars kan standard förfråganstyp för Parametrar för anskaffning och sourcing användas.

## <a name="the-sealed-bidding-process"></a>Stängd budgivningsprocess

Stängd budgivning följer nästan samma process som beskrivs i [Översikt över anbudsförfrågan](request-quotations.md). Den största skillnaden är att anbudsdata och dess bilagor hålls krypterade tills anbudet öppnas.

> [!IMPORTANT]
> [Enkäter](/dynamicsax-2012/appuser-itpro/view-and-respond-to-questionnaires) är inte krypterade och ska inte användas för att samla in känslig information

Här är en översikt över processen:

1. Du skapar och skickar en anbudsförfrågan till en eller flera leverantörer.
1. Leverantörer svarar genom att lämna in sitt stängda anbud.
1. Du öppnar anbuden efter utgångstid för anbudsförfrågan.
1. Anbuden blir synliga och du kan utvärdera och jämföra dem.
1. När ett anbud har accepterats genererar du en inköpsorder, skapar ett inköpsavtal eller uppdaterar en inköpsrekvisition.

### <a name="create-an-rfq-case-that-uses-sealed-bidding"></a>Skapa ett förfrågansärende som använder stängd budgivning.

Processen för att skapa ett förfrågansärende för stängd budgivning är nästan densamma som processen för öppen budgivning. Information om hur du skapar båda typerna av anbudsförfrågan finns i [Skapa en anbudsförfrågan](tasks/create-request-quotation.md). I det här avsnittet finns några viktiga saker att tänka på när du skapar en anbudsförfrågan för stängd budgivning.

Anbudsförfrågansärenden för stängd budgivning måste ha värdet *Stängd* för **Anbudstyp**. Det finns tre sätt att tilldela det här värdet till ett anbudsförfrågansärende:

- Ställ in värdet direkt på anbudsförfrågansärendet när du har skapat det.
- Definiera stängd budgivning som standard för alla anbudsförfrågansärenden i Parametrar för anskaffning och sourcing. (Se föregående avsnitt [Ställ in standard anbudstyp](#set-default-bid-type).)
- När du skapar ett nytt anbudsförfrågansärende väljer du en förfråganstyp som konfigureras för stängd budgivning. (Se avsnittet [Ställ in standard anbudstyp](#set-default-bid-type).)

För stängd budgivning avgör anbudsförfrågansärendets värde för **Utgångsdatum och tid** när de lämnade anbuden kan öppnas. Värdet **Utgångsdatum och tid** på varje rad matchar värdet i rubriken.

Du kan inte ändra anbudstyp efter att ett anbudsförfrågansärende har skickats.

### <a name="vendors-respond-to-an-rfq"></a>Leverantörer svarar på en anbudsförfrågan

Leverantörer som svarar på stängd budgivning använder samma procedur som när de svarar i öppen budgivning, vilket beskrivs i [Arbeta med anbudsförfrågningar i arbetsytan för leverantörsanbud](vendor-collaboration-work-customers-dynamics-365-operations.md#working-with-rfqs-in-the-vendor-bidding-workspace). Detaljerade instruktioner om hur du arbetar med både öppen och stängd budgivning finns i [Gå till och jämför anbudsförfrågansanbud och tilldela kontrakt](tasks/enter-compare-rfq-bids-award-contracts.md). Den enda skillnaden mellan stängda och öppna anbud är att inköpspersonal inte kan öppna ett stängt leverantörsanbud innan anbudsperioden är slut. Det är bara en kontaktperson för leverantören som kan öppna den leverantörens stängda anbud.

> [!IMPORTANT]
> Vid stängd budgivning kan leverantörer enbart ladda upp bilagor i PDF-format. Inga andra format godkänns.

När en registrerad leverantörsanvändare har valt **Anbud** i en anbudsförfrågan med stängd budgivning kan de ange sin anbudsinformation och den informationen hålls säker. Leverantörer kan spara sitt arbete när de förbereder ett anbud, återkomma till det så ofta det krävs och sedan skicka det när det är klart. Leverantörer kan också visa sitt bud efter att de skickat det. Om leverantörer måste ändra sitt anbud efter att de skickat det kan de återkalla det, uppdatera det och skicka det på nytt när som helst tills anbudsperioden utgår.

Följande villkor gäller under stängd budgivning:

- Under stängd budgivning skapar systemet en journal för *Anbudsförfrågan*.
- När en leverantör skickar ett anbud skapas journaler för anbudsförfrågan utan rader för ett stängt pris.
- När ärendet öppnas skapas journaler för anbudsförfrågan med pris och belopp. Du öppnar journalen genom att välja **Journaler för anbudsförfråg** på sidan **Alla anbudsförfrågningar**.
- I systemet sparas en logg över varje åtgärd som användare utför för stängd budgivning. Åtgärderna inkluderar att visa, redigera och spara anbudet. Loggen är synlig för både leverantören och för inköpspersonal som har tillgång till anbudet.
- Medan anbudet behandlas kan inköpspersonal visa dess status. Status blir antingen *Leverantör uppdaterar* eller *Skickat av leverantör*.
- Status för raderna i stängd budgivning kvarstår som *Skickat* tills anbudet öppnas.
- Om leverantören väljer att avvisa ett anbud får budets **Svarsförlopp** status *Avvisat av leverantör*. Denna status visas för inköpspersonal.
- Svar i enkäter sparas **inte** i krypterad form i databasen. Därför är de inte stängda. De kommer dock inte att vara synliga i användargränssnittet för anbudsförfrågan förrän ärendet har öppnats.

### <a name="all-sealed-bid-activities-are-logged"></a>Alla stängda budgivningsaktiviteter loggas

En detaljerad logg registrerar alla användaraktiviteter och åtgärder för ett anbud. Med aktivitetsloggen kan organisationer avgöra vem som uppdaterade ett anbud under dess livstid och vilka uppdateringar som gjordes. Det ger även organisationer möjlighet att kontrollera att endast behöriga har tillgång till ett stängt anbud. Aktivitetsloggen finns på respektive anbuds **aktivitetssida**.

### <a name="review-rfq-activity"></a>Granska aktivitet för anbudsförfrågan

Alla interaktioner med anbudet loggas och kan visas på sidan **Aktivitet**. Illustrationen nedan visar ett exempel.

![Exempel på aktivitetssidan](media/sealed-bidding-rfq-activity.png "Exempel på aktivitetssidan")

Leverantörer kan komma åt sidan **Aktivitet** genom att välja **Aktivitet** på sidan **Anbudsförfrågan för stängd budgivning**. Inköpspersonal kan komma åt den genom att välja **Aktivitet** på sidan **Anbudsförfrågan**. Aktivitetsloggen ger full insyn för leverantörer och för inköpspersonal som har kommit åt anbudet. Därför kan all obehörig åtkomst avslöjas.

### <a name="unseal-sealed-bids"></a>Öppna stängda anbud

När värdet för **Utgångsdatum och tid** som konfigurerats för ett anbudsförfrågansärende med stängd budgivning har passerats blir knappen **Öppna** tillgänglig. Välj **Öppna** för att öppna alla anbud för valt anbudsförfrågansärende. All anbudsinformation och bilagor blir då synliga så att svar på ärendet kan hanteras. Dessutom skapas journaler som innehåller inskickad anbudsinformation.

Öppnandet loggas och kan visas på sidan **Aktivitet**.

### <a name="process-accepted-bids"></a>Behandla accepterade bud

Processen för att jämföra och godkänna tidigare stängda anbud är densamma som processen för öppna bud. Information om hur du räknar, jämför, nekar och godkänner öppnade anbud finns i [Gå till och jämför anbudsförfrågansanbud och tilldela kontrakt](tasks/enter-compare-rfq-bids-award-contracts.md).

## <a name="the-rfq-activity-log-can-never-be-deleted"></a>Aktivitetsloggen för anbudsförfrågan kan aldrig raderas

Inte ens administratörer och Microsoft Support kan redigera eller radera aktivitetsloggen för anbudsförfrågan. Denna begränsning gör det enklare att se till att den stängda budgivningen är rättvis. Det blir också enklare att se till att ett korrekt redovisningsspår underhålls.
