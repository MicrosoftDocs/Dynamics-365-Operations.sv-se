---
title: Optimera planerade BYOD batchjobb
description: I den här artikeln beskrivs hur du optimerar prestanda när du använder funktionen ta med din egen databas (BYOD) med Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: Platform update 36
ms.openlocfilehash: 4df60a82e016ec8f3ba6ba0d70c261824961d221
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848325"
---
# <a name="optimize-byod-scheduled-batch-jobs"></a>Optimera planerade BYOD batchjobb


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I den här artikeln beskrivs hur du optimerar prestanda när du använder funktionen ta med din egen databas (BYOD). Mer information om BYOD finns i [ta din egen databas (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

## <a name="performance-considerations-for-data-export"></a>Prestandaöverväganden för dataexport

Efter att entiteter har publicerats till destinationsdatabasen kan du använda funktionen Export i arbetsytan **Datahantering** för att flytta data. Med hjälp av funktionen Export kan du definiera ett jobb för datarörelse som innehåller en eller flera enheter. Mer information om dataexportera finns i [översikt över dataimport- och exportjobb](../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

Du kan använda sidan **Export** för att exportera data till olika måldataformat, till exempel en CSV-fil (kommaseparerade värden). Den här sidan stöder också SQL-databaser som ett annat mål.

Du kan skapa ett dataprojekt som har flera entiteter och använda ett batch-jobb för att schemalägga det dataprojekt som ska köras. Om du väljer alternativet **Exportera i batch** kan du schemalägga jobbet för dataexport så att det körs regelbundet.

För att bevara den övergripande tillförlitligheten för BYOD-exporten måste du vara försiktig när du lägger till flera enheter i ett exportprojekt. När du bestämmer hur många enheter som ska läggas till i samma projekt bör du överväga följande parametrar:

- Entiteternas komplexitet
- Den förväntade datavolymen per enhet
- Den tid som krävs för att exporten ska slutföras på jobbnivå

För bästa prestanda bör du undvika att lägga till hundratals entiteter i ett enda projekt. Vi rekommenderar att du skapar flera jobb som vart och ett innehåller färre enheter.

## <a name="scheduling-byod-batch-jobs"></a>Tidsplanera BYOD batchjobb

För att minska påverkan på användare av Microsoft Dynamics 365 Human Resources, kör BYOD-batchjobb på natten eller efter timmar. Kontrollera tids zonen för återkommande batchjobb. Vissa batchjobb kan använda Pacific Standard Time (PST).

För att undvika prestandaproblem bör du ta hänsyn till följande faktorer när du konfigurerar planeringsfrekvensen för BYOD-batchjobb:

- Den tid som krävs för att slutföra varje batch-jobb
- Affärsbehovet för uppgifterna i BYOD

Ställ in frekvensen för varje batch-jobb med ett värde som säkerställer att jobbet kan slutföras innan nästa schemalagda körningstid. Undvik att köra flera jobb parallellt, eftersom den här metoden kan påverka personalens prestanda negativt.

För bästa prestanda bör du alltid använda alternativet **Exportera i batch** på sidan **Exportera** för att du vill tidsplanera BYOD-batchjobb. Undvik att schemalägga återkommande exporter vid **hantering \> hantera återkommande datajobb**.

## <a name="incremental-export"></a>Stegvis export

När du lägger till en enhet för dataexport kan du göra antingen en stegvis push-överföring (export) eller en fullständig push-överföring. En fullständig push-överföring tar bort alla befintliga poster från en enhet i BYOD-databasen. Sedan infogas den aktuella uppsättningen poster från entiteten personal.

Om du vill utföra en stegvis push-överföring måste du aktivera ändringsspårning för varje entitet på sidan **entiteter**. Mer information finns i [Aktivera ändringsspårning för entiteter](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

Om du väljer en stegvis push-överföring är den första push-tiden alltid en fullständig push-överföring. SQL spårar ändringar från den första fullständiga push-överföringen. När en ny post infogas, eller när en post uppdateras eller tas bort återspeglas ändringen i målentiteten.

## <a name="time-outs"></a>Timeout

Här är standard timeout för BYOD exporter:

- Tio minuter för trunkering
- En timme för massinfoga

När volymerna är höga kan det hända att dessa timeout-inställningar inte räcker. Om du vill uppdatera dem går du till **Datahantering \> Ramverksparametrar \> Ta med din egen databas**. Dessa tidsgränser är företagsspecifika och måste anges separat för varje företag.

## <a name="known-limitations"></a>Kända begränsningar

BYOD-funktionen har följande begränsningar:

- Det ska inte finnas några aktiva lås i databasen under synkroniseringen. Aktiva lås kan medföra att data skrivs över eller till och med misslyckas när de exporteras till din Azure SQL-databas.
- Du kan inte exportera sammansatta enheter till din egen databas. Sammansatta entiteter stöds för närvarande inte. Du måste exportera enskilda enheter som utgör den sammansatta enheten. Du kan dock exportera båda entiteterna i samma dataprojekt.
- Entiteter som inte har unika nycklar kan inte exporteras med hjälp av stegvis push-överföring. Den här begränsningen kan vara särskilt användbar när du försöker att inkrementellt exportera poster från en del färdiga entiteter. Eftersom dessa entiteter har utformats för att möjliggöra import av data har de ingen unik nyckel.

## <a name="troubleshooting"></a>Felsökning

### <a name="incremental-push-doesnt-work-correctly"></a>Stegvis push-överföring fungerar inte korrekt

**Utfärda:** när en fullständig push-överföring görs för en entitet visas en stor uppsättning poster i BYOD när du använder uttrycket **Select**. När du gör en stegvis push-överföring ser du dock bara några få poster i BYOD. Det verkar som om den stegvisa push-överföringen tog bort alla posterna och bara lagt till de ändrade posterna i BYOD.

**Lösning:** Tabellen SQL ändringsspårning kanske inte är i förväntat tillstånd. I fall av den här typen rekommenderar vi att du inaktiverar spårning av ändringar för enheten och sedan slår på den igen. Mer information finns i [Aktivera ändringsspårning för entiteter](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

### <a name="staging-tables-arent-clearing"></a>Mellanlagringsregister rensas inte

**Problem:** När du använder mellanlagring för projektet rensas inte mellanlagringsregistren på rätt sätt. Datan i registren fortsätter sedan att växa, vilket leder till prestandaproblem.

**Lösning:** Sju dagars historik bibehålls i mellanlagringsregistren. Historiska data som är äldre än sju dagar tas automatiskt bort från mellanlagringsregistren av batchjobbet **Importera/exportera rensning av mellanlagring**. Om detta jobb fastnar kommer registren inte att rensas korrekt. Om du startar om batchjobbet fortsätter processen så att mellanlagringsregistren rensas automatiskt.

## <a name="see-also"></a>Se även

[Översikt över datahantering](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[Ta med din egen databas (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[Översikt över jobb för import och export av data](../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[Aktivera ändringsspårning för enheter](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
