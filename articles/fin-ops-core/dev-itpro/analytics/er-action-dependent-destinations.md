---
title: Konfigurera åtgärdsberoende ER-destinationer
description: Det här ämnet beskriver hur du konfigurerar åtgärdsberoende destinationer för ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument.
author: NickSelin
manager: AnnBe
ms.date: 02/09/2021
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 80624e286fd1300b8de6fd8a7fc67c246cb3a41b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569645"
---
# <a name="configure-action-dependent-er-destinations"></a>Konfigurera åtgärdsberoende ER-destinationer

[!include [banner](../includes/banner.md)]

Du kan konfigurera [destinationer](electronic-reporting-destinations.md) för varje utdatakomponent (mapp eller fil) för ett [elektronisk rapportering (ER)](general-electronic-reporting.md) [format](general-electronic-reporting.md#FormatComponentOutbound) [konfiguration](general-electronic-reporting.md#Configuration) som används för att generera ett utgående dokument. Användare som kör ett ER-format av den här typen och som har rätt åtkomstbehörighet kan också ändra de konfigurerade destinationsinställningarna vid körning.

I Microsoft Dynamics 365 Finance **version 10.0.17 och senare**, kan ett ER-format köras genom [etablera](er-apis-app10-0-17.md) en åtgärdskod som användaren utför genom att köra det ER-formatet. Till exempel i modulen **Kundreskontra**, i inställningarna för utskriftshantering kan du välja ett ER-format som genererar ett specifikt affärsdokument, till exempel en fritextfaktura. Du kan sedan välja **Vy** om du vill förhandsgranska fakturan eller **Skriv ut** om du vill skicka den till en skrivare. Om en användaråtgärd överförs för det körande ER-formatet vid körning, kan du konfigurera olika ER-destinationer för olika användaråtgärder. I det här avsnittet beskrivs hur du konfigurerar ER-destinationer för den här typen av ER-format.

## <a name="make-action-dependent-er-destinations-available"></a>Gör åtgärdsberoende ER-destinationer tillgängliga

För att konfigurera åtgärdsberoende ER-destinationer i den aktuella Finance-instansen och aktivera [ny](er-apis-app10-0-17.md) ER API, öppna arbetsytan [Funktionshantering](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) och aktivera funktionen **Konfigurera specifika ER-destinationer som ska användas för olika PM-åtgärder**. Att använda konfigurerade ER-destinationer för rapporter [specifika](#reports-list-wave1) vid körning, ska du aktivera funktionen **Flödesutmatning av PM-rapporter baserade på ER-destinationer som är specifika för användaråtgärder (cykel 1)**.

## <a name="configure-action-dependent-er-destinations"></a>Konfigurera åtgärdsberoende ER-destinationer

När du aktiverar funktionen **Konfigurera specifika ER-destinationer som ska användas för olika PM-åtgärder** kan du konfigurera åtgärdsberoende ER-destinationer på snabbfliken **Fildestination** på sidan **Destination för elektronisk rapportering**. För varje komponent kan du lägga till en post och aktivera specifika ER-destinationer. För varje post måste du ange den typ av dokument som de konfigurerade ER-destinationerna ska tillämpas på. I fältet **Dokumenttyp**, välj ett av följande värden:

- Välj **Elektronisk** om du vill använda de konfigurerade destinationerna om ingen användaråtgärdskod anges under körning.
- Välj **Utskriftshantering** om du vill använda de konfigurerade destinationerna om en användaråtgärdskod anges under körning.
- Välj **Någon** om du alltid vill använda de konfigurerade destinationerna oavsett om en användaråtgärd anges under körning.

Om du väljer dokumenttypen **Utskriftshantering** måste du ange de användaråtgärder som de konfigurerade ER-destinationerna ska ansökas om. I fältet **Utskriftshanteringsåtgärd**, välj ett av följande värden:

- Välj **Vy** om du vill använda de konfigurerade destinationerna om användaråtgärden **Vy** anges under körning.
- Välj **Skriv ut** om du vill använda de konfigurerade destinationerna om användaråtgärden **Skriv ut** anges under körning.
- Välj **Skicka** om du vill använda de konfigurerade destinationerna om användaråtgärden **Skicka** anges under körning.

> [!NOTE]
> Flera åtgärder kan väljas för en målpost.

Om du väljer dokumenttyp **Någon** väljs **Automatisk identifiering** automatiskt i fältet **Utskriftshanteringsåtgärd** som en användaråtgärd, och följande beteende inträffar:

- Om ingen användaråtgärdskod tillhandahålls vid körning tillämpas alla konfigurerade ER-destinationer.
- Om en användaråtgärdskod tillhandahålls vid körning tillämpas en ER-destination som är fördefinierad för en specifik åtgärd, **oavsett om den har aktiverats eller inte**:

    - När åtgärden **Vy** anges under körning används ER-destinationen **skärm** används.
    - När åtgärden **Skicka** anges under körning används ER-destinationen **e-post** används.
    - När åtgärden **Skriva ut** anges under körning används ER-destinationen **Skrivare** används.

Du kan till exempel använda ER-formatet **Fritextfaktura (Excel)** för att skriva ut en [fritextfaktura](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/create-free-text-invoice-new) när du bokför den. Om du vill dirigera ett genererat dokument måste du konfigurera ER-destinationer för det här ER-formatet. Du kanske till exempel måste konfigurera dessa ER-destinationer så att du kan utföra följande på ett genererat dokument:

- Arkivera dokumentet om ER-formatet körs men ingen åtgärdskod anges (till exempel när dokumentet skickas elektroniskt).
- Förhandsgranska dokumentet i en webbläsare när en användare utför **vy**-åtgärden.
- Arkivera och skriv ut dokumentet när en användare utför **utskriftsåtgärden**.
- Arkivera dokumentet och skicka det med e-post som bilaga i ett utgående e-postmeddelande när en användare utför åtgärden **Skicka**.

I följande bild visas hur du kan uppnå detta konfigurerar ER-destinationer som uppsättning individuella destinationsposter när varje post konfigureras för en enskild användaråtgärd:

![Målsida för elektronisk rapportering med åtgärdsberoende målinställningar för ett ER-format när varje målpost konfigureras för en enskild användaråtgärd](./media/er-destination-action-dependent-01.png)

I följande bild visas hur du kan uppnå detta konfigurerar ER-destinationer som uppsättning individuella destinationsposter när varje post konfigureras för en enskild destination:

![Målsida för elektronisk rapportering med åtgärdsberoende målinställningar för ett ER-format när varje målpost konfigureras för en enskild användardestination](./media/er-destination-action-dependent-01a.png)

> [!NOTE]
> Om en åtgärdskod tillhandahålls för det körande ER-formatet, men inga destinationer har konfigurerats för den åtgärdskoden, kommer [standard](electronic-reporting-destinations.md#default-behavior) målbeteende tillämpas.

## <a name="change-action-dependent-er-destinations-at-runtime"></a>Ändra åtgärdsberoende ER-destinationer vid körning

När ett ER-format körs, om användaråtgärder har tillhandahållits av användare som har rätt [behörigheter](electronic-reporting-destinations.md#security-considerations) för att ändra konfigurerade destinationsinställningar vid körning visas en dialogruta som ger möjlighet att ändra de konfigurerade destinationsinställningarna. Den här dialogrutan är valfri och utseendet beror på hur anropet som ER-ramverket gör för att köra ett ER-format har implementerats. Om den här dialogrutan visas kommer ER-destinationer i den att aktiveras enligt den användaråtgärd som tillhandahålls.

Följande illustration visar ett exempel på dialogrutan **destinationer i elektroniskt rapporteringsformat** som visas när en fritextfaktura [bokförs](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/create-free-text-invoice-new) och ER-formatet **fritextfaktura invoice (Excel)** körs för att skapa dokumentet om åtgärden **skrivare** tillhandahölls och ER-destinationer konfigurerades för det här formatet som visas tidigare i detta ämne.

![Dialogruta som ger möjlighet att ändra de initialt konfigurerade ER-destinationera för det körande ER-formatet](./media/er-destination-action-dependent-02.gif)

> [!NOTE]
> Om du konfigurerat ER-destinationer för flera komponenter i det körande ER-formatet, erbjuds ett alternativ separat för alla konfigurerade komponenter i ER-formatet.

## <a name="verify-the-provided-user-action"></a>Kontrollera den angivna användaråtgärden

Du kan kontrollera vilken användaråtgärd som eventuellt vidtas för att köra ER-formatet när du utför en viss användaråtgärd. Denna verifiering är viktig när du måste konfigurera åtgärdsberoende ER-destinationer, men du är inte säker på vilken användaråtgärdskod, om det finns någon sådan, tillhandahålls. Till exempel när du börjar lägga upp en fritextfaktura och ställer in alternativet **Skriv ut faktura** till **Ja** i dialogrutan **Bokför fritextfaktura** kan du ange alternativet **Använd destination för utskriftshantering** till **Ja** eller **Nej**.

Följ dessa steg för att verifiera den användaråtgärdskod som finns.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. I dialogrutan **Användarparametrar** [ange](er-trace-reports-compare-baseline.md#configure-er-parameters-to-use-the-baseline-feature) alternativet **Kör i felsökningsläge** till **Ja**.
4. Utför en användaråtgärd genom att köra ett ER-format. Kom ihåg att ER-användarparametrar är företagsspecifika och användarspecifika.
5. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfiguration av felsökningsloggar**.
6. På sidan **Konfiguration av felsökningsloggar**, filtrera ER-körloggarna för att hitta loggen för din ER-formatkörning.
7. Granska loggposterna som måste innehålla den post som presenterar den angivna användaråtgärdskoden, om någon åtgärd har tillhandahållits för ER-formatkörningen.

    ![Sidan Elektronisk rapporteringskörning loggar som innehåller information om användaråtgärdskoden som har angetts för den filtrerade körningen av ett ER-format.](./media/er-destination-action-dependent-03.png)

## <a name=""></a><a name="reports-list-wave1">Lista över affärsdokument (cykel 1)</a>

Följande lista över affärsdokument styrs av funktionen **Flödesutmatning av PM-rapporter baserade på ER-destinationer som är specifika för användaråtgärder (cykel 1)**:

- Kundfaktura (fritextfaktura)
- Kundfaktura (försäljningsfaktura)
- Inköpsorder
- Inköpsförfrågan för inköpsorder
- Bekräftelse av försäljningsorder
- Kravbrevsnotering
- Kontoutdrag för kund
- Räntefaktura
- Betalningsavi för leverantör
- Anbudsförfrågan

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)

[Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)

[Ändringar av API:et för ramverket för elektronisk rapportering för Application update 10.0.17](er-apis-app10-0-17.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]