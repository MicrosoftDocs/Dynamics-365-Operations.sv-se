---
title: Arbeta med funktionsinställningar
description: I den här artikeln beskrivs hur du konfigurerar e-fakturor.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 23466a53bb8ba597503aaa12d41395fc82b9f14e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904337"
---
# <a name="work-with-feature-setups"></a>Arbeta med funktionsinställningar

[!include [banner](../includes/banner.md)]

Om du vill ställa in genereringen av elektroniska filer och andra bearbetningssteg (t.ex. filer med digital signerin, skicka dem till statens webbtjänst och ta emot svar eller lagra dem), ställer du in bearbetningsförloppet, tillämplighetsregler och variabler för e-faktureringsfunktioner.

Inställningsinformationen kombineras i begreppet *funktionskonfiguration* och kan skapas, tas bort och justeras. För slutförda versioner av e-faktureringsfunktioner kan informationen också visas.

Du kan skapa så många objekt för funktionskonfiguration som du behöver för att kunna ange olika scenarier för generering, bearbetning och mottagning av elektroniska filer. Även om dessa inställningsobjekt för funktioner har oberoende bearbetningsåtgärder och villkor för körning, skapas de som en del av en enskild e-faktureringsfunktion och ärver dess livscykel och distributionsprocess.

## <a name="add-a-feature-setup"></a>Lägg till funktionskonfiguration

1. Logga in på ditt konto för Regelkonfigurationstjänst (RCS).
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Funktioner**, välj panelen **e-faktura**.
3. På sidan **Funktioner för e-fakturering** väljer du en funktionsversion för e-fakturering som har statusen **Utkast**.
4. På fliken **Inställningar** väljer du **Lägg till**.
5. I listrutedialogen **Skapa funktionskonfiguration**, i fältgruppen **Ny**, väljer du ett av följande alternativ:
 
    - **Anpassade inställningar** – Skapa en ny funktionsinställning med tomma kanaler, en tom lista över bearbetning av försäljningsförloppet, ett tomt avsnitt för tillämplighetsregler och en standarduppsättning variabler, beroende på inställningstyp.
    - **Från funktionsinställningarna** – Skapa en kopia av en annan funktionsinställning inom ramarna för den aktuella e-faktureringsfunktionen.

6. Om du valde alternativet **Anpassad inställning** i det senaste stege anger du ett namn och en beskrivning för funktionens inställningsobjekt innan du, i fältrgruppen **Inställningstyp**, väljer ett av följande alternativ:

    - **Bearbetning av pipeline** – Välj det här alternativet om du vill generera och bearbeta utgående elektroniska dokument. För den här inställningstypen skapar systemet en tom lista för bearbetning av pipeline, ett tomt avsnitt för tillämplighetsregler och en standarduppsättning variabler. Du kommer inte att kunna arbeta med kanalerna för inkommande elektroniska dokument.
    - **Datakanal** – Välj detta alternativ om du vill ställa in processen för mottagning av inkommande elektroniska dokument från en av de definierade kanalerna och skicka dem direkt till Microsoft Dynamics 365 Finance eller Dynamics 365 Supply Chain Management utan ytterligare åtgärder. För den här inställningstypen skapar systemet en fördefinierad parameterlista för datakanaler, ett tomt avsnitt för tillämplighetsregler och en uppsättning standardvariabler. Du kan inte lägga till några åtgärder i bearbetningsförloppet.
    - **Datakanal och bearbetning av pipeline** – Denna inställningstype liknar inställningstypen **Datakanal**. Innan ett inkommande elektroniskt dokument skickas till Ekonomi eller Supply Chain Management kan du dock ställa in ytterligare åtgärder i bearbetningsförloppet.

7. Om du valde alternativet **Datakanal** eller **Datakanal och bearbetning av pipeline** i det senaste steget måste du välja vilken kanal som ska integreras med i fältet **Välj datakanal**.
8. Markera **Skapa**.

När en funktionsinställning har skapats kan du välja **Redigera** för att konfigurera den.

## <a name="edit-a-feature-setup"></a>Redigera funktionsinställningar

Beroende på vilken typ av funktionsinställning du har kan du konfigurera processen för att generera utgående elektroniska filer och skicka dem till externa kanaler, alernativt ta emot inkommande dokument och skicka dem till ditt program för Ekonomi eller Supply Chain Management.

### <a name="data-channel"></a>Datakanal

En *datakanal* tar den elektroniska filen och bearbetar den eller skickar den direkt till Ekonomi eller Supply Chain Management. Detta alternativ är inte tillgängligt för funktionsinställningar av typen **Bearbeta pipeline**.

När du vill ställa in en datakanal anger du kanalens namn. Definiera sedan parametrarna, baserat på den valda kanaltypen. Datakanal-ID:t måste referera till variabeln som skapas specifikt för att identifiera datakanalen. Det kommer att användas som referens i Ekonomi- eller Supply Chain Management.

På fliken **Bilagsfilter** gör du definiera en uppsättning filter för att hämta specifika filer från kanalen. Du kan skapa flera rader om du förväntar dig att filerna kommer att ha olika filnamnstillägg, eller om filer måste bearbetas på olika sätt beroende på filnamn. Här är huvudparametrarna:

- **Namn** – Ange namnet på den fil som systemet ska referera till under bearbetningen. I programmen Ekonomi och Supply Chain Management kommer du att kunna se filerna i sändningsloggen.
- **Filter** – Definiera filtret för att välja filer.
- **Tillval** – Om den här kryssrutan är avmarkerad krävs filen. I så fall visas ett felmeddelande i systemet om kanalerna inte innehåller filer som motsvarar filtret. Denna parameter kan användas i e-postmeddelanden.

Om kanalen är en brevlåda och ett inkommande e-postmeddelande innehåller flera bilagor, kan du konfigurera regler för att definiera hur tjänsten ska hantera bilagor. Tjänsten kan betrakta varje bilaga som en separat e-faktura, eller också kan den betrakta en bilaga som en huvudfaktura och alla andra bilagor som tillägg.

### <a name="processing-pipeline"></a>Bearbetar pipeline

En *bearbetningspipeline* är en uppsättning *åtgärder* som körs efter varandra tills de har slutförts. Du kan använda en bearbetningspipeline för att ställa in processen för att generera elektroniska filer och utföra andra steg (t.ex. signera filer digitalt, skicka dem till externa webbtjänster och analysera svaret, samt ta emot och bearbeta inkommande dokument).

Listan med åtgärder är fördefinierad. Med knapparna **Ny** och **Ta bort** kan du ange kombinationen av åtgärder som logiskt definierar den process som krävs för att skicka eller ta emot dokument.

Åtgärdernas ordningsföljd är mycket viktig. Du kan justera ordningen genom att använda knapparna **Upp** och **Ned**.

Varje åtgärd har en uppsättning parametrar som du kan konfigurera eller justera. Den specifika parameteruppsättning som används beror på åtgärdens typ.

- **Åtgärd** – Välj typ av åtgärd.
- **Åtgärdsnamn** – Ange namnet på åtgärden. Det här namnet visas i inlämningsloggar och i meddelanden i Ekonomi- och Supply Chain Management-program.
- **Beskrivning** – Ange mer information om syftet med åtgärden i processen.
- **Aktivera nytt försök** – Om du markerar den här kryssrutan kan du välja en åtgärd i fätet **Testa åtgärd igen** och konfigurera ytterligare parametrar på fliken **Testa parametrar igen**.

    Med funktionen Försök igen kan du konfigurera tjänstens beteende om en viss åtgärd inte kan köras. Om till exempel den externa webbtjänsten som du försöker ansluta till inte svarar, kan du ange hur många gånger som systemet ska försöka utföra anslutningen, med vilka intervall samt från vilken åtgärd i bearbetningsförloppet.

- **Exportera resultat** – Du kan markera den här kryssrutan för *en* åtgärd i bearbetningsförloppet. Den elektroniska fil som åtgärden skapar i programmet Ekonomi eller Supply Chain Management kan sedan exporteras från sidan **Sändningslogg för elektroniska dokument**.

### <a name="applicability-rules"></a>Tillämplighetsregler

*Tillämplighetsregler* är konfigurerbara satser som ger ett sammanhang för körning av funktioner för e-fakturering via de e-faktureringsfunktionerna.
Affärsdokument som skickas från Ekonomi eller Supply Chain Management till e-fakturering har ingen explicit referens som gör det möjligt för e-faktureringsfunktionen att anropa en viss funktionsversion samt ett specifikt objekt för funktionsinställning i syfte att bearbeta överföringen. När ett affärsdokument emellertid konfigureras korrekt innehåller det emellertid de nödvändiga elementen för att e-faktureringen ska kunna bestämma vilken funktionsversion för e-fakturering samt vilken bearbetningspipeline som måste väljas och sedan köras.

Tillämplighetsregler för det möjligt för e-faktureringstjänsten att hitta de exakta funktionerna för e-fakturering som måste användas för att bearbeta en överföring. För att hitta rätt funktioner matchas fälten **Kontext** från det skickade affärsdokumentet mot satserna från tillämplighetsreglerna.

Du kan arbeta med tillämpbarhetsregler på följande sätt:

- Välj **Ny** om du vill lägga till en ny sats i en uppsättning tillämplighetsregler.
- Välj **Ta bort** för att ta bort en sats.
- Välj flera poster och använd knappen **Gruppera** elller **Avgruppera** om du vill skapa en kombination av artiklar eller logiska utdrag. Välj till exempel de rader du vill gruppera och välj sedan **Gruppsats**. När satser grupperas läggs en ny kolumn till i rutnätet. Den här kolumnen anger den logiska operatorn för den grupperade satsen. Följande typer av operatorer stöds:

    - Equal
    - Not equal
    - Större än/mindre än
    - Större än eller lika med/mindre än eller lika med
    - Contains
    - Börja med

    > [!NOTE]
    > När du delar upp en sats ska du alltid börja med den innersta grupperingsnivån.

### <a name="variables"></a>Variabler

*Variabler* ger dig mer flexibilitet när du ställer in ett bearbetningsförlopp och dataflödet mellan åtgärder. I vissa åtgärdsparametrar kan du referera till en variabel för att tillfälligt lagra data eller elektroniska filer. Vissa variabler används för att överföra data mellan Ekonomi- eller Supply Chain Management-program och e-faktureringstjänsten.

Systemet skapar vissa variabler som standard. Variabeln **BusinessDocumentDataModel** innehåller till exempel affärsdata i en JSON-struktur (JavaScript Object Notation) som kommer i anropet från det anslutna programmet under sändningsprocessen.

Följande typer av variabler är tillgängliga:

- **Konstant** – En behållare för lagring av tillfälliga data som används vid bearbetning av åtgärder för försäljningsförlopp.
- **Från klient** – variabelns innehåll hämtas från Dynamics 365-klienten när överföringsprocessen körs.
- **Till klient** – Variabelns innehåll görs tillgängligt för import av Dynamics 365-klienten när överföringsprocessen körs.
- **Datatyp** – Välj datatyp för informationen som lagras i variabeln.

### <a name="parameters"></a>Parametrar

Alternativet **Inaktivera affärsdatareducering** används för att optimera strukturen hos affärsdatans nyttolast som kommer från programmet Ekonomi eller Supply Chain Management under sändning av elektroniska dokument. Med optimering minskar du de data som finns i e-faktureringstjänsten för vidare transformering till den elektroniska fil som krävs. Standardvärdet är **Nej**.

- **Ja** – Ekonomi eller Supply Chain Management skickar en JSON-fil av strukturen för **Fakturamodell** eller **Skattemodell** (för Brasilien) som definieras i modulen **Elektronisk rapportering**. Alla element i modellen fylls med affärsdata på programsidan, oavsett den slutgiltiga elektroniska filstrukturen. Modeller innehåller vanligtvis mer affärsdata än målfilstrukturen kräver, och mer tid kan krävas för att generera denna data i programmet. Värdet **Ja** för detta alternativ krävs i de sällsynta fall då du vill generera olika utdatafiler i en enda e-faktureringsfunktion och uppsättning av funktioner. Värdet **Ja** är användbart när du felsöker scenarier, strukturen på elektroniska filer och fullständigheten hos affärsdata.
- **Nej** – Ekonomi eller Supply Chain Management utför det första anropet till tjänsten utan affärsdata. Syftet med detta anrop är att få information om den elektroniska rapporteringskonfiguration (ER) som ska användas för elektronisk filtransformering i bearbetningsförloppet. Denna information returneras till programmet, som använder den för att ta reda på vilken underuppsättning av affärsdata som ska ingå i JSON-filen med struktur för **Fakturamodell** eller **Skattemodell** (för Brasilien). Värdet **Nej** för det här alternativet minskar volymen av affärsdata som programmet skickar till tjänsten, detta eftersom programmet bara kan skicka de affärsdata som krävs för att en elektronisk fil ska kunna genereras.

### <a name="validate-a-feature-setup"></a>Validera en funktionskonfiguration

Du kan köra en validering för att kontrollera att hela konfigurationen är konsekvent. Om till exempel en obligatorisk parameter för en åtgärd har lämnats tom kommer valideringen att upptäcka denna inkonsekvens och skicka ett varningsmeddelande till dig.

- På sidan **Inställning av funktionsversion** i åtgärdsfönstret väljer du **Validera**.

## <a name="delete-a-feature-setup"></a>Ta bort en funktionskonfiguration

1. På sidan **Funktioner för e-fakturering** väljer du en funktionsversion för e-fakturering som har statusen **Utkast**.
2. På fliken **Konfigurationer** väljer du **Ta bort**.
3. I meddelanderutan som visas väljer du **Ja** för att bekräfta att du vill ta bort funktionsinställningarna.
