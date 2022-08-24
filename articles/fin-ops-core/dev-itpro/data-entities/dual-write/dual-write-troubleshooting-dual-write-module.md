---
title: Felsöka problem med dubbelriktad skrivning i appar för ekonomi och drift
description: Den här artikeln innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem med dubbelriktad skrivning i appar för ekonomi och drift.
author: RamaKrishnamoorthy
ms.date: 04/18/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 5678cd38e48eb5226e36851679436d3b6c117cf9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289587"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>Felsöka problem med dubbelriktad skrivning i appar för ekonomi och drift

[!include [banner](../../includes/banner.md)]



Den här artikeln innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan appar för ekonomi och drift och Dataverse. Den ger i synnerhet information som kan hjälpa dig att åtgärda problem med modulen **Dubbelriktad skrivning** i appar för ekonomi och drift.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Du kan inte läsa in modulen för dubbelriktad skrivning i en app för ekonomi och drift

Om du inte kan öppna sidan **dubbelriktad skrivning** genom att välja panelen **dubbelriktad skrivning** i arbetsytan **datahantering** är dataintegreringstjänsten förmodligen nere. Skapa en supportbiljett för att begära en omstart av dataintegreringstjänsten.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Fel vid försök att skapa en ny tabellmappning

**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Samma användare som ställer in dubbelriktad skrivning.

Följande felmeddelande kan visas när du försöker konfigurera en ny tabell för dubbelriktad skrivning. Den enda användare som kan skapa en mappning är den användare som ställer in anslutningen med dubbelriktad skrivning.

*Svarsstatuskoden anger inte slutförande: 401 (obehörig)*.

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Fel vid öppning av användargränssnittet med dubbelriktad skrivning

Följande felmeddelande kan visas när du försöker komma åt dubbelriktad skrivning från arbetsytan **Datahantering**:

*login.microsoftonline.com vägrade att ansluta.*

Om du vill åtgärda problemet loggar du in på ett InPrivate-fönster i Microsoft Edge, ett inkognitofönster i Chromium eller ett inkognitofönster i Google Chrome. Du måste också häva blockeringen eller rensa cookies från tredje part.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Fel vid länkning av miljön för dubbelriktad skrivning eller tillägg av en ny tabellmappning

**Erforderlig roll för att åtgärda problemet:** Systemadministratör i både appar för ekonomi och drift och Dataverse.

Du kan stöta på följande fel när du länkar eller skapar mappningar:

```dos
Response status code does not indicate success: 403 (tokenexchange).
Session ID: \<your session id\>
Root activity ID: \<your root activity\> id
```

Det här felet kan uppstå om du inte har tillräcklig behörighet för att länka dubbelriktad skrivning eller skapa mappningar. Det här felet kan också uppstå om Dataverse-miljön återställdes utan att dubbelriktig skrivning avlänkas. Alla användare med rollen systemadministratör i både appar för ekonomi och drift och Dataverse kan länka dessa miljöer. Det är bara användaren som installerar anslutningen för dubbelriktad skrivning som kan lägga till nya tabellmappningar. Efter installationen kan alla användare med rollen systemadministratör övervaka status och redigera mappningarna.

## <a name="error-when-you-stop-the-table-mapping"></a>Fel när du stoppar tabellmappningen

Följande felmeddelande kan visas när du försöker att stoppa tabellmappningen:

*\[Förbjudet\], \[{"status":403,"source":"","message":"Fel från token exchange: Användaren har inte rätt att komma åt anslutning dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Fjärrservern returnerade ett fel: (403) Förbjudet.*

Det här felet uppstår när den länkade Dataverse-miljön inte är tillgänglig.

Lös problemet genom att skapa en biljett till dataintegreringsteamet. Koppla nätverksspårningen så att dataintegreringsteamet kan markera mappningarna som **Inte körs** i servern.

## <a name="enable-parallel-processing-in-finance-and-operations-apps-to-improve-performance"></a>Aktivera parallell bearbetning i appar för ekonomi och drift för att förbättra prestandan

Att aktivera parallell bearbetning kan minska den tid som behövs för att importera data från Dynamics 365-appar för kundengagemang och Microsoft Dataverse till appar för ekonomi och drift. 

Slutför följande steg för att aktivera parallell bearbetning i appar för ekonomi och drift.

1. Logga in i din miljö för ekonomi och drift.
2. Gå till **Datahantering > Ramverksparametrar**.
3. Välj **Enhetsinställningar** och sedan **Konfigurera parametrar för enhetskörning**.
4. Lägg till parametrarna för parallell bearbetning:
    - **Importera tröskelvärde för postantal** – Det antal poster som måste uppfyllas innan parallell bearbetning aktiveras.
    - **Importera uppgiftsantal** – Antalet trådar (uppgifter) som ska köras parallellt.
5. Välj **Spara**.


## <a name="errors-while-trying-to-start-a-table-mapping"></a>Fel vid försök att starta en tabellmappning

### <a name="unable-to-complete-initial-data-sync"></a>Det gick inte att slutföra den första datasynkroniseringen

Följande felmeddelande kan komma att visas när du försöker köra den första datasynkroniseringen:

*Det gick inte att slutföra inledande datasynkronisering. Fel: del i dubbelriktad skrivning – registrering av plugin-program misslyckades: Det gick inte att skapa metadata för sökning för dubbelriktad skrivning.*

Du kan komma att få detta felmeddelande när du försöker ange statusen för en mappning som **Körs**: Korrigeringen beror på orsaken till felet:

+ Om mappningen har beroende mappningar ska du se till att aktivera de beroende mappningarna för den här tabellmappningen.
+ Mappningen kanske saknar käll- eller målkolumner. Om en kolumn i appen för ekonomi och drift saknas följer du stegen i avsnittet [Problem med tabellkolumner som saknas i mappningar](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Om en kolumn i Dataverse saknas klickar du på knappen **Uppdatera tabeller** på mappningen så att kolumnerna automatiskt fylls i igen i mappningen.

### <a name="version-mismatch-error-and-upgrading-dual-write-solutions"></a>Versionsmatchningsfel och uppgradering av lösningar med dubbelriktad skrivning

Följande felmeddelanden kan komma att visas när du försöker köra tabellmappningarna:

+ *Kundgrupper (msdyn_customergroups) : Fel vid dubbelskrivning – Dynamics 365 for Sales-lösningen "Dynamics365Company" har versionsfel. Version: "2.0.2.10" Erforderlig version: "2.0.133"*
+ *Dynamics 365 for Sales-lösningen "Dynamics365FinanceExtended" har ett versionsfel. Version: "1.0.0.0" Erforderlig version: "2.0.227"*
+ *Dynamics 365 for Sales-lösningen "Dynamics365FinanceAndOperationsCommon" har ett versionsfel. Version: "1.0.0.0" Erforderlig version: "2.0.133"*
+ *Dynamics 365 for Sales-lösningen "CurrencyExchangeRates" har ett versionsfel. Version: "1.0.0.0" Erforderlig version: "2.0.133"*
+ *Dynamics 365 for Sales-lösningen "Dynamics365SupplyChainExtended" har ett versionsfel. Version: "1.0.0.0" Erforderlig version: "2.0.227"*

Du korrigerar problemen genom att uppdatera lösningsar med dubbelskrivning i Dataverse. Se till att du uppgraderar till den senaste lösningen som matchar erforderlig lösningsversion.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

