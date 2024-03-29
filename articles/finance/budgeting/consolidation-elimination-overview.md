---
title: Översikt över konsolidering och eliminering
description: Det här avsnittet innehåller allmän information om konsoliderings- och kvittningsprocessen. Avsnittet innehåller alla svar på vanliga frågor och svar.
author: panolte
ms.date: 11/11/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidate
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13151"
- intro-internal
ms.assetid: 9d8f55cb-b2cf-4e01-89cf-0e21f5c8ae1f
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 757c7634fc929ead018d1ddcca4cc223c1a95638
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779918"
---
# <a name="consolidation-and-elimination-overview"></a>Översikt över konsolidering och eliminering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller allmän information om konsoliderings- och kvittningsprocessen. Avsnittet innehåller alla svar på vanliga frågor och svar.

När du konsoliderar data kombineras de ekonomiska resultaten för flera dotterbolag till resultat för ett enda, konsoliderat företag. Dotterbolag kan finnas på andra versioner eller system, de kanske inte är helägda och de kan använda andra valutor. Det finns flera alternativ för konsolidering av data:

-   **Konsolidera online** – Konsoliderar dagliga saldon efter valda konton och dimensioner och sparar dem i ett konsolideringsföretag.
-   **Ekonomisk rapportering** – Aktiverar konsolidering av transaktioner och saldon och kan genereras när som helst. Flera nivåer för hierarkier kan skapas, och flera rapporteringsvalutor kan visas.
-   **Konsolidera med import** – Importerar saldon till ett konsolideringsföretag.
-   **Exportera företagsbalanser** – Innehåller en exportfil av företagssaldon. Filen kan sedan importeras till andra instanser eller system. Den ekonomiska rapporteringen kan också användas för exporten saldon till en Microsoft Excel-fil.

Elimineringar kan rapporteras på flera sätt:

-  Elimineringsregler kan ställas in i systemet och sedan bearbetas under konsolideringen eller via ett elimineringsförslag. Reglerna kan bokföras till alla företag som har alternativet **Använd för ekonomisk elimineringsprocess** markerat i inställningarna av juridisk enhet.
-   Ett separat företag kan skapas och användas för att bestämma manuellt och bokföra elimineringstransaktioner. Företaget kan användas i konsolideringen eller i ekonomisk rapportering.
-  Kontona och ekonomiska dimensioner som används för att fastställa koncernintern aktivitet kan filtreras på en raddefinition eller kolumndefinition i ekonomisk rapportering och fullständiga vidaresökningsfunktioner går att använda. En beräknad kolumn eller rad sedan kan användas för att ta bort konton och ekonomiska dimensioner från den konsoliderade summan.

Det finns många konsolideringsscenarier, och varje metod hanterar scenarierna på olika sätt.

## <a name="frequently-asked-questions"></a>Vanliga frågor
Jag vill bokföra elimineringar i en databas. Vilka är alternativen?
 - Du har flera alternativ. Du kan använda alternativet **Konsolidera online** och inkluderar elimineringar under processen eller som ett förslag. Transaktionerna bokförs i konsolideringsföretaget. Alternativt kan du ha ett separat företag som du skapar manuellt skapar elimineringarna i, och sedan använder i ekonomisk rapportering eller i konsolideringen.

Du behöver våra konsolideringsresultat i flera flera rapporteringsvalutor.
 - Alternativet **Ekonomisk rapportering** har obegränsade rapporteringsvalutor. Data översätts under rapportgenereringen baserat på valutakurstypen och valutaomräkningsmetoden som anges på huvudkontot. Eftersom **Konsolidera online** bara har en rapportvaluta, krävs ett konsoliderat företag för varje rapportvaluta om du använder detta alternativ. Alternativet **Ekonomisk rapportering** är den rekommenderade metoden.

Jag vill visa detaljer på transaktionsnivån för varje företag.
 - Alternativet **Ekonomisk rapportering** är lösningen, eftersom detaljer på transaktionsnivån kan visas för så många företag som ingår i rapportträddefinitionen.

Vi använder budgetplanering eller budgetkontroll, och den måste konsolideras.
 - **Ekonomisk rapportering** är lösningen som konsoliderar alla data i budgetplaneringen eller budgetkontrollen.

Våra dotterbolag finns över hela världen, och därför har vi flera kontoplaner. Vilken är den bästa metoden för konsolidering?
- Du har flera alternativ när du måste hantera flera kontoplaner. Du kan använda alternativet **Konsolidera online** och välja antingen konsolideringskontot som definieras på huvudkontot eller en konsolideringskontogrupp. Du kan också använda alternativet **Ekonomisk rapportering**, inkludera flera länkar till ekonomiska dimensioner i raddefinitionen och mappa kontona.

Vi vill ha flera nivåer av konsolidering. Med andra ord, först konsoliderar vi alla våra europeiska dotterbolag till det brittiska pundet (GBP). Sedan tar vi uppgifterna och översätter det konsoliderade beloppet till USD. Hur kan du göra detta?
- När det behövs flera nivåer av konsolidering och olika valutor används vid varje nivå, måste du använda **Konsolidera online**. Flera konsolideringsföretag måste skapas som har olika redovisningar och rapporteringsvalutor. Konsolideringen måste sedan köras flera gånger. Alternativet **Ekonomisk rapportering** översätter alltid från varje källföretags redovisningsvaluta till den valda valutan.

Vi har dotterbolag på ett annat system. Hur kan vi konsolidera dem?
- Använd alternativet **Konsolidera med import** för att hämta saldona till ett konsolideringsföretag.

Vissa av våra dotterbolag är inte helägda. Vilken är den bästa metoden för konsolidering?
- Du har flera alternativ för delägda dotterbolag. Genom att använda alternativet **Ekonomisk rapportering** kan du definiera en rapportträddefinition och ägare. Du kan också använda en beräknad rad eller kolumner som motsvarar det delägda beloppet. Du kan även visa minoritetsintresset som en egen rad i en rapport. Du kan också använda alternativet **Konsolidera online**. Fliken **Juridiska personer** har kolumnen **Äganderätt** där du kan definiera procentandelen som ägs av moderbolaget.

Vår organisation måste visa konsolideringar efter affärsenheten eller kan använda organisationshierarkierna.
- Alternativet **Ekonomisk rapportering** är lösningen. Organisationshierarkier som har juridiska personer eller ekonomiska dimensioner kan rapporteras i ekonomisk rapportering. Du kan även skapa egna hierarkier med flera nivåer med hjälp av en rapportträddefinition som har en kombination av juridiska personer och dimensionsvärden.

Vi har mer än en instans av systemet.
- Genom att använda alternativet **Exportera företagsbalanser** för att exportera från en instans och sedan använda **Konsolidera med import** på den andra instansen kan du konsolidera data.

Kan jag göra en konsolidering med min budget i statusen **UTKAST**? 
- Du kan inte bearbeta eller slutföra budgetar i konsolideringsföretaget. Vi rekommenderar att du använder Financial Reporting när du konsoliderar utkastbudgetar.

Mer information finns i [Valutaomräkning i ett konsolideringsföretag](../general-ledger/currency-revaluation-consolidation-company.md).




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
