---
title: Skapa en ny ER-lösning för att skriva ut ZPL-etiketter
description: I det här ämnet beskrivs hur du utformar en ny elektronisk rapporteringslösning (ER) för att skriva ut en Zebra Programming Language-etiketter (ZPL).
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: c1bedf1184b45741102000fa68c8d662c7383301
ms.sourcegitcommit: 2977e92a76211875421e608555311c363cfbdc25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2022
ms.locfileid: "8612368"
---
# <a name="design-a-new-er-solution-to-print-zpl-labels"></a>Skapa en ny ER-lösning för att skriva ut ZPL-etiketter

[!include [banner](../includes/banner.md)]


Detta ämne förklarar hur en användare i rollerna systemadministratör, elektronisk rapportutvecklare eller funktionskonsult för elektronisk rapportering kan konfigurera parametrar för ramverket för [elektronisk rapportering (ER)](general-electronic-reporting.md), utforma nödvändiga ER-[konfigurationer](general-electronic-reporting.md#Configuration) för en ny ER-lösning för att komma åt data i lagerstyrningssystemet, samt skapa anpassade etiketter för lagerplats i Zebra Programming Language (ZPL) II-format. Dessa steg kan slutföras i **USRT**-företaget.

## <a name="business-scenario"></a>Affärsscenario

Du representerar ett företag som implementerat lagerstyrning i Microsoft Microsoft Dynamics 365 Finance. Alla lagerställen måste märkas med en självhäftande som innehåller en streckkod. Lagerarbetare använder streckkodsläsare för att skanna streckkoderna.

Alla lagerställen har märkts inom ramarna för aktiviteter före aktivering. Du måste dock också kunna skriva ut platsetiketter för lagerställen på begäran om befintliga etiketter skadas eller om lagerställets hyllor omkonfigureras. Med den nyligen frisläppta ER-funktionen kan du konfigurera en ny ER-lösning som gör att en lageransvarig kan skriva ut etiketter direkt på en etikettskrivare.

## <a name="configure-the-er-framework"></a>Konfigurera ER-ramverket

Följ stegen i [Konfigurera ER-ramverket](er-quick-start2-customize-report.md#ConfigureFramework) för att ställa in den minimala uppsättningen ER-parametrar. Du måste slutföra dessa inställningar innan du börjar använda ER-ramverket för att designa en ny ER-lösning.

## <a name="design-a-domain-specific-data-model"></a>Ange urvalskriterier i dialogrutan för frågeformulär

Skapa en ny ER-konfiguration som innehåller en [datamodell](er-overview-components.md#data-model-component)-komponent för domänen för lagerstyrning. Denna datamodell kommer senare att användas som datakälla när du designar ett ER-format för att generera lagerställesetiketter.

### <a name="import-a-data-model-configuration"></a>Importera en konfiguration för datamodell

Följ anvisningarna nedan och importera önskad datamodell från en XML-fil som tillhandahålls av Microsoft. Du kan också skapa din egen datamodell på det sätt som beskrivs i nästa avsnitt.

1. Hämta filen [Warehouse model.version.1.xml](https://download.microsoft.com/download/9/f/1/9f136e9b-bf5f-403a-b089-a2b2ed1da2ba/Warehouse-model.version.1.xml) och spara den på den lokala datorn.
2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.
4. På sidan **Konfigurationer**, i åtgärdsfönstret, väljer du **Exchange** \> **Läs in från XML-fil**.
5. Välj **Bläddra** och leta sedan reda på och markera filen **Warehouse model.version.1.xml**.
6. Välj **OK** för att importera konfigurationen.

![Importerad konfiguration av ER-datamodell på sidan Konfigurationer.](./media/er-design-zpl-labels-imported-model.png)

### <a name="create-a-data-model-configuration"></a>Skapa en datamodellkonfiguration

Istället för att importera den Microsoft-tillhandahållna datamodellfilen kan du skapa en datamodell från grunden. Ett exempel på hur du utför den här uppgiften finns i [Skapa en ny datamodellkonfiguration](er-quick-start1-new-solution.md#DesignDataModel).

### <a name="review-the-data-model"></a>Granska datamodellen

Du kan visa en redigerbar version av den konfigurerade datamodellen på sidan **Datamodelldesigner**.

![Struktur för ER-datamodellen på sidan Datamodelldesigner.](./media/er-design-zpl-labels-model.png)

## <a name="design-a-model-mapping-for-the-configured-data-model"></a>Designa en modellmappning för den konfigurerade datamodellen

Som användare i rollen som elektronisk rapporteringsutvecklare måste du skapa en ny ER-konfiguration som innehåller en [modellmappning](er-overview-components.md#model-mapping-component)-komponent för lagerdatamodellen. Denna komponent implementerar den konfigurerade datamodellen för Dynamics 365 Finance och är specifik för den appen. Du måste konfigurera den för att ange vilka programobjekt som ska användas för att fylla i den konfigurerade datamodellen med programdata vid körning. För att slutföra den här uppgiften måste du förstå hur datastrukturen i affärsdomänen för lagerstyrning implementeras i Ekonomi.

### <a name="import-a-model-mapping-configuration"></a>Importera en ny konfiguration för modellmappning

Följ dessa steg för att importera önskad modellmappning från en XML-fil som tillhandahålls av Microsoft. Du kan också skapa din egen modellmappning på det sätt som beskrivs i nästa avsnitt.

1. Hämta filen [Warehouse model mapping.version.1.xml](https://download.microsoft.com/download/1/c/c/1cc94d28-3d90-4ffd-a118-77d6c322904f/Warehouse-model-mapping.version.1.1.xml) och spara den på den lokala datorn.
2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.
4. På sidan **Konfigurationer**, i åtgärdsfönstret, väljer du **Exchange** \> **Läs in från XML-fil**.
5. Välj **Bläddra** och leta sedan reda på och markera filen **Warehouse model mapping.version.1.1.xml**.
6. Välj **OK** för att importera konfigurationen.

![Importerad mappningskonfiguration av ER-modell på sidan Konfigurationer.](./media/er-design-zpl-labels-imported-mapping.png)

### <a name="create-a-model-mapping-configuration"></a>Skapa konfiguration för modellmappning

Istället för att importera den Microsoft-tillhandahållna modellmappningsfilen kan du skapa en modellmappning från grunden. Ett exempel på hur du utför den här uppgiften finns i [Skapa en ny modellmappningskonfiguration](er-quick-start1-new-solution.md#CreateModelMapping).

### <a name="review-the-model-mapping"></a>Granska modellmappningen

Du kan visa en redigerbar version av den konfigurerade modellmappningan en på sidan **Modellmappningsdesigner**.

![Struktur för ER-modellmappningen på sidan Modellmappningsdesigner.](./media/er-design-zpl-labels-mapping.png)

## <a name="design-a-format"></a>Designa ett format

Som användare i rollen funktionell konsult för elektronisk rapportering måste du skapa en ny ER-konfiguration som innehåller komponenten [format](er-overview-components.md#format-component). Om du vill konfigurera den här komponenten använder du ZPL II-kod för att ange layouten på lagerställesetiketten.

### <a name="import-a-format-configuration"></a>Importera en formatkonfiguration

Följ anvisningarna nedan för att importera önskat format från en XML-fil som tillhandahålls av Microsoft. Du kan också skapa ditt eget format på det sätt som beskrivs i nästa avsnitt.

1. Hämta filen [Warehouse location labels.version.1.1.xml](https://download.microsoft.com/download/5/7/5/5758b551-69a5-45bd-a2b2-21c3db73a6fc/Warehouse-location-labels.version.1.1.xml) och spara den på den lokala datorn.
2. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
3. På arbetsytan **Elektronisk rapportering** väljer du **Rapporteringskonfiguration**.
4. På sidan **Konfigurationer**, i åtgärdsfönstret, väljer du **Exchange** \> **Läs in från XML-fil**.
5. Välj **Bläddra** och leta sedan reda på och markera filen **Warehouse location labels.version.1.1.xml**.
6. Välj **OK** för att importera konfigurationen.

![Importerad ER-formatkonfiguration på sidan Konfigurationer.](./media/er-design-zpl-labels-imported-format.png)

### <a name="create-a-format-configuration"></a>Skapa en formatkonfiguration

Istället för att importera den Microsoft-tillhandahållna formatfilen kan du skapa ett format från grunden. Ett exempel på hur du utför den här uppgiften finns i [Skapa en ny formatkonfiguration](er-quick-start1-new-solution.md#FormatCreate).

### <a name="review-the-format"></a>Granska formatet

Du kan visa en redigerbar version av det konfigurerade formatet på sidan **Formatdesigner**.

![Struktur för ER-formatet på sidan Formatdesigner.](./media/er-design-zpl-labels-format.png)

Datakällan `model.Location.Label` för det här formatet är konfigurerad till att generera etiketter som innehåller följande information:

- Lagerställetiteln som text
- Lagerställetiteln som en streckkod
- Platsens titel
- Kontrollsiffror

På sidan **Formeldesigner** för datakällan innehåller ER-formeln `CONCATENATE` som används för att generera etiketter en funktion som kombinerar informationen i önskad layout.

![Formel för datakällan på sidan Formeldesigner.](./media/er-design-zpl-labels-review-formula.png)

> [!TIP]
> Etikettlayouten är utformad så att platstitel och kontrollsiffror stämmer justeras i mitten av etiketten. ZPL II stöder dock inte centerjusteringen för streckkoder. Därför används formeln för `model.Location.Warehouse.Alignment`-datakällan för justering av streckkoden mitt på etiketten. Denna formel beräknar den vänstra förskjutningen av streckkoden, baserat på antalet tecken i lagerställesrubriken.

## <a name="prepare-your-environment-for-previewing-generated-labels"></a>Förbered din miljö för förhandsgranskning av genererade etiketter

I följande exempel används ett emulatorprogram för skrivare för ZPL-etiketter i syfte att visa en förhandsgranskning av genererade etiketter på skärmen. Följ dessa steg om du vill aktivera detta alternativ.

1. Lägg till ER-målet [Skrivare](er-destination-type-print.md) för ER-formatet för **lagerställets platsetikett** och konfigurera det så att genererade etiketter skickas från Ekonomi till [rutt-agenten för dokument (DRA)](install-document-routing-agent.md).
2. Installera och konfigurera DRA för att dirigera genererade etiketter från Ekonomi till en lokal skrivare som kan nås från den aktuella arbetsstationen.
3. Lägg till en lokal skrivare för den aktuella arbetsstationen och konfigurera den för att skicka genererade etiketter från DRA-skrivaren till ett skrivaremulatorprogram.
4. Installera ett skrivaremulatorprogram som ett tillägg i webbläsaren Chrome, och konfigurera det att skicka genererade etiketter från en lokal skrivare till en webbtjänst som återger genererade etiketter och returnerar dem till skrivaremulatorn för förhandsgranskning.

<table>
<tbody>
<tr align="center">
<td>
<p>Finance</p>
<p>ER-rapport</p>
<p>Skrivardestination</p>
</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from Finance to the DRA."></td>
<td>Dokumentflödesagent</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from the DRA to a local printer."></td>
<td>Lokal skrivare</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from a local printer to a printer emulator."></td>
<td>Skrivaremulator</td>
<td><img src="./media/er-design-zpl-labels-flow2.png" alt="Data flow direction: from a printer emulator to a rendering web service and then back to the printer emulator."></td>
<td>Återge webbtjänst</td>
</td>
</tr>
</tbody>
</table>

### <a name="install-and-configure-a-printer-emulator-application"></a>Installera och konfigurera ett skrivaremulatorprogram

Lägg till ett skrivarmeulatorprogram för ZPL-återgivningsmotorn i webbläsaren Chrome. I det här exemplet används [Zpl](https://chrome.google.com/webstore/detail/zpl-printer/phoidlklenidapnijkabnfdgmadlcmjo)-skrivaremulatorn som baseras på [webbtjänsten Labelary ZPL](http://labelary.com/service.html). Skrivaremulatorprogrammet skickar genererade etiketter i ZPL-format från en lokal skrivare till webbtjänsten och returnerar sedan etiketter som PDF- eller PNG-filer för förhandsgranskning.

1. Sök efter och välj det skrivaremulatorprogram som du vill använda i Chrome-webbutiken. Välj sedan **Lägg till i Chrome** om du vill lägga till det i webbläsaren Chrome.

    ![Lägga till skrivaremulatorprogrammet i webbläsaren Chrome från Chrome-webbutiken.](./media/er-design-zpl-labels-add-app.png)

2. Välj **Starta programmet** för att köra skrivaremulatorprogrammet från webbläsaren Chrome.

    ![Köra skrivaremulatorprogrammet från webbläsaren Chrome.](./media/er-design-zpl-labels-run-app.png)

3. Konfigurera program som körs:

    1. Stäng programmet.
    2. Ställ in värden på **127.0.0.1** i skrivarinställningarna.
    3. Ställ in porten på **9100**.

        ![Konfigurera emulatorprogrammet för skrivare.](./media/er-design-zpl-labels-configure-app.png)

    4. Starta programmet igen. Du bör få ett meddelande om att skrivaren har startats på den angivna värddatorn och på den angivna porten.

        ![Skrivaremulatorprogrammet aktiveras igen.](./media/er-design-zpl-labels-turn-on-app.png)

> [!NOTE]
> Eftersom skrivarprogrammet som används i det här exemplet använder sig av en webbtjänst för att återge etiketter bör du se till att dina säkerhetsinställningar gör det möjligt för dig att kommunicera med tjänsten. Annars får inte programmet de återgivna etiketterna och ingen förhandsgranskning av dessa etiketter är tillgänglig.

### <a name="add-and-configure-a-local-printer"></a>Lägga till och konfigurera en lokal skrivare

[Lägg till en ny lokal skrivare](https://support.microsoft.com/windows/install-a-printer-in-windows-10-cc0724cf-793e-3542-d1ff-727e4978638b) som den aktuella skrivaren kan använda för att skicka genererade etiketter från DRA till skrivaremulatorprogramvaran.

1. I Windows väljer du **Start** \> **Inställningar** \> **Enheter** \> **Skrivare \& skannrar**.
2. Välj **Inställningar för skrivare \& skannrar**.
3. För **Lägg till en skrivare eller skanner** väljer du **Lägg till enhet**.
4. För **Den skrivare jag vill ha listas inte** väljer du **Lägg till manuellt**.
5. I fältet **Hitta en skrivare på annat sätt** väljer du **Lägg till en lokal skrivare eller nätverksskrivare med manuella inställningar**.
6. I fältet **Välj en skrivarport** väljer du **Skapa en ny port** och följer sedan dessa steg:

    1. I fältet **Porttyp** väljer du **Standard TCP/IP-port**.
    2. I fältet **Värddatornamn eller IP-adress** anger du **127.0.0.1**.
    3. I fältet **Portnamn** anger du **ZPL**.
    4. Vänta tills åtgärden **Söker TCP/IP-port** har slutförts.
    5. I fältet **Enhetstyp** väljer du **Anpassad** och sedan **Inställningar**.
    6. Kontrollera att följande portinställningar är angivna:

        - **Portnamn:** ZPL
        - **Skrivarnamn eller IP-adress:** 127.0.0.1
        - **Protokoll:** Raw
        - **Portnummer:** 9100

7. I fältet **Installera skrivardrivrutin** väljer du **Allmän / Endast text**.
8. I fältet **Skrivarnamn** anger du **ZebraPrinter**.

![Lägga till en lokal skrivare för den aktuella enheten.](./media/er-design-zpl-labels-configure-printer.png)

### <a name="install-and-configure-the-dra"></a>Installera och konfigurera DRA

Förbered DRA för att skicka genererade etiketter från Ekonomi till den konfigurerade lokala skrivaren.

1. [Installera DRA](install-document-routing-agent.md#install-the-document-routing-agent).
2. [Konfigurera DRA](install-document-routing-agent.md#configure-the-document-routing-agent).
3. [Registrera den lokala skrivaren](install-document-routing-agent.md#register-network-printers) i DRA.
4. [Aktivera den lokala skrivaren](install-document-routing-agent.md#administer-network-printers) i din Ekonomi-miljö.

![Förbereda DRA för utskrift av genererade etiketter.](./media/er-design-zpl-labels-configure-dra.png)

### <a name="configure-the-er-destination"></a>Konfigurera ER-mål

Förbered ER-målet för att skicka genererade etiketter från Ekonomi till DRA.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Elektroniska rapporteringsmål**.
2. På sidan **Elektronisk rapportering** väljer du **Ny** i åtgärdsfönstret.
3. I fältet **Referens** väljer du **Lagerställeetiketter**.
4. På snabbflikarna **Fildestination** välj **Ny**.
5. I fältet **Namn** anger du **Etiketter**.
6. I fältet **Filkomponentnamn** väljer du **Rapport**.
7. Välj **inställningar**.
8. I dialogrutan **Målinställningar**, på fliken **Skrivare**, anger du alternativet för **Aktiverad** som **Ja**.
9. I fältet **Skrivarnamn** väljer du **ZebraPrinter**.
10. I fältet **Dirigeringstyp för dokument** väljer du **ZPL**.
11. Välj **OK**.

![Konfigurera ER-målet för format på lagerställeetiketter på målsidan för elektronisk rapportering.](./media/er-design-zpl-labels-configure-destination.png)

## <a name="review-warehouse-locations"></a>Granska lagerställesplatser

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Lager** \> **Platser**.
2. Filtrera på sidan **Platser** om du bara vill visa platser som har ett värde i fältet **Kontrollera siffror**.

![Granska lagerställen på sidan Platser.](./media/er-design-zpl-labels-review-locations.png)

## <a name="print-warehouse-location-labels"></a>Skriva ut platsetiketter för lagerställen

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer**, i konfigurationsträdet, expanderar du **Modell för lagerställe** och väljer **Lagerställeetiketter**.
3. Klicka på **Kör** i åtgärdsfönstret.
4. I dialogrutan **Parametrar för elektronisk rapport**, på fliken **Poster att inkludera**, väljer du **Filter**.
5. På fliken **Område** letar du upp raden där fältet **Tabell** har angetts som **Platser** och fältet **Fält** är inställt på **Plats**. I fältet **Kriterier** anger du **LPEnabled**.
6. Välj **OK**.
7. Välj **OK**. En etikett skapas och visas på förhandsgranskningssidan i skrivaremulatorprogrammet.

![Granska en genererad etikett på förhandsgranskningssidan i Zpl-skrivaremulatorprogrammet.](./media/er-design-zpl-labels-preview-label.png)

## <a name="modify-the-layout-of-a-label"></a>Ändra layouten på en etikett

Du kan ändra den aktuella layouten på etiketterna för lagerställe. Följande exempel visar hur du ändrar layouten så att genererade etiketter inkluderar ett platsprofil-ID.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. Ange [ER-användarparametern](electronic-reporting-destinations.md#applicability) för **Använd destinationer för utkaststatus** som **Ja**.
3. På sidan **Konfigurationer**, i konfigurationsträdet, expanderar du **Modell för lagerställe** och väljer **Lagerställeetiketter**.
4. Välj **Designer**.
5. På sidan **Formatdesigner**, på fliken **Mappning**, väljer du datakällan `model.Location.Label`.
6. I dialogrutan **Egenskaper för datakälla** väljer du **Redigera** \> **Redigera formel**.
7. På sidan **Formeldesigner**, i fältet **Formel**, granskar du den ER-formel som används för att generera etiketter.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^XZ")
    ```

8. Uppdatera formeln om du vill lägga till ett platsprofil-ID för genererade etiketter.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^CF0,40,40^FO0,240^FB800,1,0,C,0^FD",@.ProfileID,"\&^FS",CrLf,
    "^XZ")
    ```

9. Välj **Spara**.
10. Välj **OK**.
11. Klicka på **Kör** i åtgärdsfönstret.
12. I dialogrutan **Parametrar för elektronisk rapport**, på fliken **Poster att inkludera**, väljer du **Filter**.
13. På fliken **Område** letar du upp raden där fältet **Tabell** har angetts som **Platser** och fältet **Fält** är inställt på **Plats**. I fältet **Kriterium** anger du **Bay**.
14. Välj **OK**.
15. Välj **OK**. En etikett skapas och visas på förhandsgranskningssidan i skrivaremulatorprogrammet.

![Granska en genererad etikett som inkluderar ett platsprofil-ID på förhandsgranskningssidan i Zpl-skrivaremulatorprogrammet.](./media/er-design-zpl-labels-preview-label2.png)

## <a name="encoding"></a>Kodning

> [!NOTE]
> Du måste synkronisera kodningsinställningen för komponenten **Common\\File** i det redigerbara ER-formatet och lämplig inställning för den utformade etiketten. Värdet på fältet **[Kodning](er-suppress-bom-characters.md)** i komponenten **Common\\File** bör inte motsäga ett ZPL-kommando som används för att styra etikettkodningen (till exempel kommandot `^CI`). ER kontrollerar inte att dessa inställningar är synkroniserade.

## <a name="additional-resources"></a>Ytterligare resurser

[Skrivardestination](er-destination-type-print.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
