---
title: Serviceorder
description: En serviceorder representerar ett besök av en servicetekniker hos en kund ett specifikt datum.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b049b166edf2b5a318a4b1af85e7f74cfe433f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437353"
---
# <a name="service-orders"></a>Serviceorder   

[!include [banner](../includes/banner.md)]


En serviceorder representerar ett besök av en servicetekniker hos en kund ett specifikt datum. Varje serviceorder består av en eller flera serviceorderrader. Serviceorderrader representerar de arbetstimmar som måste utföras av serviceteknikern samt artiklar, utgifter och avgifter.

Du kan koppla uppgifter och objekt till en serviceorderrad. Du kan sedan gruppera serviceorderrader efter vilken uppgift eller av objektet. Du kan även koppla artiklar som listas i lagret till serviceorderrader.

## <a name="create-service-orders"></a>Skapa serviceorder

Du kan skapa serviceorder utifrån serviceavtalet och raderna för avtalet. Du kan dock skapa serviceorder som är kopplade till ett serviceavtal endast under den period som anges i avtalet. Om ett serviceavtal är giltig för kalenderåret 2011 kan skapa du serviceorder för avtalet från den 1 januari 2011 och den 31 December 2011.

Du kan skapa serviceorder individuellt utan att associera dem till ett avtal. Dessa kan användas för att hantera en enstaka eller oplanerat servicebesök. I mars vill kunden ha service utförd på två maskiner utöver dem som har angetts i serviceavtalet. För den här uppgiften skapar du serviceorder men associerar inte dem med ett avtal.


> [!NOTE]
> <P>Om du vill skapa serviceorder som inte är associerade med ett serviceavtal måste du välja kryssrutan <STRONG>Tillåt utan serviceavtal</STRONG> i formuläret <STRONG>Serviceparametrar</STRONG>.</P>

**Scenario**

I följande scenario beskrivs en annan situation där det är praktiskt att skapa en serviceorder som inte är kopplad till ett serviceavtal.

Företagets klarerare tar mot ett samtal med en begäran om akut service på en hiss. Det finns ingen tid att skapa ett serviceavtal och ett projekt. Därför skapar klareraren en serviceorder direkt i formuläret **serviceorder** och kopplar serviceordern till ett befintligt projekt och skapar serviceorderraderna. Klareraren skapa också en uppgift eller objektrelation för en befintlig serviceorder om du behöver registrera arbete som inte hör till serviceavtalet. Mer information finns i [skapa serviceorder manuellt](create-service-orders-manually.md) och [Skapa serviceuppgiftsrelationer](create-service-task-relations.md).

## <a name="monitor-the-progress-of-service-orders"></a>Övervaka förlopp för serviceorder

För att övervaka förloppet hos serviceorder genom olika grupper och arbetsprocesser kan du ställa in ett system med faser och orsakskoder för serviceorder. För varje fas kan du ange tillåtna åtgärder. Mer information finns i [Skapa orsakskoder](create-reason-codes.md).

**Exempel**

En serviceorder godkänns av klareraren. Klareraren uppdaterar fasen för serviceordern och anger en orsakskod som visar att serviceordern har frisläppts till teknikern. Serviceteknikern besöker kunden och utför serviceordern.

## <a name="specify-item-requirements-for-service-orders"></a>Ange artikelbehov för serviceorder

Du kan ange lagerartiklar som krävs för serviceorder. Dock måste serviceordern vara kopplad till ett projekt. Artikelbehov för serviceorder bearbetas via ett projekt. 

**Exempel**

Serviceorder som skapas från serviceavtalet behandlas sedan av klareraren. På den första serviceordern ser klareraren att teknikern behöver en viktig reservdel som inte finns i lager. Därför skapar klareraren ett artikelkrav för reservdelen direkt från serviceordern.

## <a name="move-and-post-lines"></a>Flytta och bokföra rader

När serviceteknikern återkommer från besöket ändrar och uppdaterar teknikern serviceorderraderna. När han är på sitt servicebesök utför han även ett servicejobb som skulle ha utförts under nästa servicebesök. Därför flyttar han raderna från det följande servicebesöket till det aktuella (E). Därefter bokför han serviceordern. Mer information finns i [Flytta serviceorderrader](move-service-order-lines.md).

## <a name="cancel-service-orders"></a>Avbryt serviceorder

En annan serviceorder som hade genererats för januari blir föråldrad eftersom jobbet annulleras. Därför annullerar serviceklareraren serviceordern. Mer information finns i [Avbryt serviceorder](cancel-service-orders.md).

## <a name="post-from-projects"></a>Bokföra från Projekt

I slutet av varje vecka vill klareraren bokföra alla serviceorder som är knutna till ett visst projekt. Därför letar klareraren reda på det relevanta projektet i formuläret **projekt** och bokför serviceorder som har slutförts. Mer information finns i [Bokföra serviceorder automatiskt (klassformulär)](https://technet.microsoft.com/library/aa574685\(v=ax.60\)).

## <a name="delete-service-orders"></a>Ta bort serviceorder

Under andra halvåret upptäcker kunden att servicebesöken inträffar alltför sällan. Du måste skapa nya, mer frekventa servicebesök för resten av serviceavtalets giltighet. Därför måste du ta bort de befintliga serviceorder som har skapats (I) och skapa nya serviceorder. Mer information finns i [Ta bort serviceorder](delete-service-orders.md).

## <a name="see-also"></a>Se även

[Serviceorder (formulär)](https://technet.microsoft.com/library/aa554361\(v=ax.60\))

  


