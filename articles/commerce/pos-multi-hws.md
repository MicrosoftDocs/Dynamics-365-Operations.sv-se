---
title: Dedikerade betalningsterminaler och fråga om skrivare och kassalåda
description: Det här ämnet ger information om möjligheten att få en dedikerad betalningsterminal och uppmanar användaren att välja en kassa låda och en kvittoskrivare.
author: rubendel
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 03cb68ede82668523e6970d33df676738e65fd83
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415858"
---
# <a name="dedicated-payment-terminals-and-prompts-for-a-printer-and-cash-drawer"></a>Dedikerade betalningsterminaler och fråga om skrivare och kassalåda

[!include [banner](includes/banner.md)]

Det här ämnet ger information om möjligheten att få en dedikerad betalningsterminal och uppmanar användaren att välja en kassa låda och en kvittoskrivare.

## <a name="overview"></a>Översikt

Moderna återförsäljare söker efter sätt att effektivisera kassaupplevelsen i butiker. Tack vare den senaste utvecklingen mot pappersfri kassa med elektroniska betalningar går det inte bara att göra köpet bättre utan också minska behovet av att ha fullständiga komplement till tillgängliga kringutrustningsenheter för varje butik.

Microsoft Dynamics 365 Commerce stöder dessa trender genom att aktivera ett scenario där en kassaenhet (POS) har tilldelats en särskild utbetalningsterminal hela tiden, men den har ingen egen kvittoskrivare eller kassalåda. När en affärspartner måste skriva ut en inleverans eller göra en kontantbetalning, uppmanas de att välja en maskinvarustation där dessa enheter konfigureras.

## <a name="key-terms"></a>Nyckeltermer

| Villkor | beskrivning |
|---|---|
| Anmäla | Den enhet som används för att konfigurera en instans av ett kassaregister. |
| Enhet | En representation av den fysiska instansen av ett kassaregister och det moderna kassaprogram som den tilldelas till. |
| Dedikerad maskinvarustation | Maskinvarustationen affärslogik inbyggd i Modern POS för Windows och Modern POS för Android-programmet. |
| Port för lådan (d/k) | En traditionell metod för att ansluta en kassalåda till en kvittoskrivare. |
| Nätverkskringutrustning | Inbyggt stöd för nätaktiverade betalningsterminaler, kvittoskrivare och kassalådor. |

## <a name="supported-pos-clients-and-devices"></a>Kassaklienter och -enheter som stöds

Funktionen som beskrivs i det här avsnittet stöds av Modern POS för Windows och Modern POS för Android POS-klienter.

Den här funktionen stöder nätaktiverade betalningsterminaler och kvittoskrivare. Du kan tillhandahålla stöd för kassalådan genom att ansluta kassalådan till den nätverksanslutna kvittoskrivaren via d/k-porten.

Medföljande stöd för den här funktionen finns i [Dynamics 365 betalningskoppling för Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3). Andra betalningskopplingar kan dock stödjas via Commerce programutvecklingskit (SDK) för betalningar. Skrivare med stöd för kvitton inkluderar nätverksanslutna kvittoskrivare från Star Micronics och Epson.

Om du vill installera kvittoskrivare använder du verktyget för Star Micronics-skrivaren för att konfigurera enheten så att den kan användas i nätverket. Detta verktyg kommer också att tillhandahålla enhetens IP-adress.

Om du vill ställa in Epson-kvittoskrivare använder du verktyget Epson ePOS-Print för att konfigurera enheten för nätverksprotokoll.

Mer information om hur du konfigurerar kringutrustning i nätverk finns i [Översikt över stöd för kringutrustning](https://go.microsoft.com/fwlink/?linkid=2129965).

## <a name="set-up-a-dedicated-payment-terminal-and-a-prompt-for-a-printer-and-cash-drawer"></a>Dedikerade betalningsterminaler och fråga om skrivare och kassalåda

### <a name="set-up-hardware-profiles"></a>Ställ in maskinvaruprofiler

Du måste ha två typer av maskinvaruprofil. Den första tilldelas kassan. Den andra har tilldelats en maskinvarustation på butiksnivå och används för logisk gruppering av nätverkskvittoskrivare och kassalådor.

#### <a name="set-up-a-hardware-profile-for-the-register"></a>Ställ in en maskinvaruprofil för kassaapparaten

Om du vill ställa in maskinvaruprofilen som är kopplad till kassaapparaten följer du stegen nedan.

1. I Dynamics 365 Commerce söker du efter **maskinvaruprofil**.
2. Välj **Ny**.
3. Tilldela ett maskinvaruprofilnummer och ange en beskrivning. Den här maskinvaruprofilen kommer att tilldelas själva kassaapparaten. Därför räcker det med en beskrivning som är **Dedikerad med reserv**.
4. På snabbflikarna för olika enhetstyper ställer du in följande enhetstyper.

    | Enhet | Typ | Enhetsnamn | Ytterligare detaljer |
    |---|---|---|---|
    | Skrivare | Reserv | *Något* | Enhetsnamnet är skiftlägeskänsligt. **Kvittoprofil-ID** ska vara detsamma som **kvittoprofil-ID** som mappas till nätverksskrivaren som har ställts in i maskinvaruprofilen som har tilldelats maskinvarustationen på kanalnivå. |
    | Kassalåda | Reserv | *Något* | Enhetsnamnet är skiftlägeskänsligt. Ange alternativet **Använda delade skift** till **Ja**. |
    | EFT-tjänst | Adyen | Inte tillämpligt | Information om hur du konfigurerar den medföljande Adyen-anslutningen, se [Dynamics 365 betalningsanslutning för Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3) Andra betalningskopplingar kan dock stödjas via [Commerce programutvecklingskit (SDK) för betalningar](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/end-to-end-payment-extension). |
    | PIN-knappsats | Nätverk | **MicrosoftAdyenDeviceV001** | Ingen. |

5. I Dynamics 365 Commerce söker du efter **register**.
6. Välj ett register genom att välja registernumret och välj sedan **Redigera**.
7. Tilldela den maskinvaruprofil som du just har skapat i kassan som ska använda en särskild betalningsterminal. Enheten som mappas till den här kassan måste använda antingen Modern POS för Windows eller Modern POS för Android-programmet.
8. Välj **Spara**.
9. I åtgärdsfönstret på fliken **Kassor** välj **Konfigurera IP-adresser**.
10. På snabbfliken **PIN-knappsats** anger du IP-adressen för betalningsterminalen. Information om hur du hämtar IP-adressen för betalningsterminalen med hjälp av Adyen-anslutaren finns i [Dynamics 365-betalningskoppling för Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3).
11. Välj **Spara**.

#### <a name="set-up-a-hardware-profile-for-the-receipt-printer-and-cash-drawer"></a>Ställa in en maskinvaruprofil för kvittoskrivaren och kassalådan

Om du vill ställa in maskinvaruprofilen som används för att gruppera skrivaren och kassalådan för nätverkskvitton följer du stegen nedan.

1. I Dynamics 365 Commerce söker du efter **maskinvaruprofil**.
2. Välj **Ny**.
3. Tilldela ett maskinvaruprofilnummer och ange en beskrivning. Den här maskinvaruprofilen används för att gruppera kvittoskrivaren och kassalådan. Därför räcker det att göra en beskrivning som till exempel **nätverksskrivare och kassalåda**.
4. På snabbflikarna för olika enhetstyper ställer du in följande enhetstyper.

    | Enhet | Typ | beskrivning | Ytterligare detaljer |
    |---|---|---|---|
    | Skrivare | Nätverk | **Epson** eller **Star** | Enhetsnamnet är skiftlägeskänsligt. **Kvittoprofil-ID** ska vara detsamma som **kvittoprofil-ID** som mappas till skrivaren som har ställts in i maskinvaruprofilen som har tilldelats kassan. |
    | Kassalåda | Nätverk | **Epson** eller **Star** | Enhetsnamnet är skiftlägeskänsligt. ange alternativet **Använda delade skift** till **Ja**. |

5. Välj **Spara**.

### <a name="set-up-hardware-stations"></a>Konfigurera maskinvarustationer

Du måste ha två maskinvarustationer. Den första kommer att mappas till kassan. Den andra kommer att väljas efter behov, när en inleverans måste skrivas ut eller en kassalåda måste öppnas.

#### <a name="register-a-hardware-station"></a>Registrera en maskinvarustation

1. I Dynamics 365 Commerce söker du efter **alla butiker**.
2. Välj en butik genom att välja dess **ID-värden för butikskanal** och välj sedan **Redigera**.
3. På snabbfliken **Maskinvarustationer** väljer du **Lägg till**.
4. Ange fältet **Maskinvarustationtyp** till **dedikerad**.
5. Ange en beskrivning men ställ inte in några andra värden för den här maskinvarustationen. Den här maskinvarustationen kommer alltid att användas för kassan. 

#### <a name="set-up-a-hardware-station-for-the-receipt-printer-and-cash-drawer"></a>Ställa in en maskinvarustation för kvittoskrivaren och kassalådan

1. I Dynamics 365 Commerce söker du efter **alla butiker**.
2. Välj en butik genom att välja dess **ID-värden för butikskanal** och välj sedan **Redigera**.
3. På snabbfliken **Maskinvarustationer** väljer du **Lägg till**.
4. Ange fältet **Maskinvarustationtyp** till **dedikerad**.
5. Ange en beskrivning. Den här maskinvarustation används för kvittoskrivaren och kassalådan.
6. I fältet **Maskinvaruprofil** väljer du maskinvaruprofilen som du har skapat för kvittoskrivaren och kassalådan.
7. Välj **Spara**.
8. Medan hårdvarustationen för mottagarskrivaren och kassalådan fortfarande är vald väljer du **Konfigurera IP-adresser**.
9. Ta reda på skrivarens IP-adress och ange den som IP-adress för både kvittoskrivaren och kassalådan.
10. Välj **Spara**
11. Sök efter **distributionsscheman**.
12. Välj distributionsschema **1090** och välj sedan **Kör nu**.
13. Välj distributionsschema **1070** och välj sedan **Kör nu**.

### <a name="set-up-the-system-to-prompt-for-receipt-printer-and-cash-drawer-selection-as-its-required"></a>Ställ in systemet för att fråga om kvittoskrivare och kassalådaval som det är obligatoriskt

1. Stäng det aktuella skiftet i en POS-klient som stöds, om ett skift är öppet.
2. Logga in och välj sedan **Åtgärder som inte berör kassalådan**.
3. Använd funktionen **Hantera maskinvarustationer** för att aktivera en maskinvarustation.
4. Välj maskinvarustationen som du skapade för kassan om du vill göra den aktiv.
5. Logga ut från kassan och logga sedan in igen och öppna ett skift.

Den betalningsterminal som tilldelas maskinvaruprofilen kommer nu alltid att vara aktiv, och du uppmanas att ange om en kvittoskrivare eller kassalåda krävs.

Många butiker som begär den här funktionen är intresserade av att minska avfall genom att tillhandahålla e-postkvitton och uppmuntra elektroniska betalningar. Beroende på kassakonfigurationen uppmanas butikspersonalen att välja en kvittoskrivare eller kassalåda först när en kund vill ha en fysisk leverans eller vill betala med kontanter.

Butikspersonalen ombeds att välja en maskinvarustation bara en gång per transaktion, såvida inte en inleverans måste skrivas ut och kontanter användas för betalning, men maskinvaruprofilen som ursprungligen valdes inkluderar inte båda enheterna. I så fall uppmanas butikspersonalen att välja en maskinvarustation som kan användas för att slutföra transaktionen.

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera POS Hybrid-app på Android och iOS](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/hybridApp)
- [Dynamics 365-betalningskoppling för Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)
- [Nätverkskringutrustning för nätverk](https://go.microsoft.com/fwlink/?linkid=2129965)
