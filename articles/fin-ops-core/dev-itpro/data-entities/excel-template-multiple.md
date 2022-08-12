---
title: Datamallar med flera kalkylblad
description: Den här artikeln beskriver hur du importerar data med hjälp av Excel-dataentitetsmallar till Ekonomi och drift.
author: peakerbl
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: f0845b111afb18205677b885c91fe1585b24ab14
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108819"
---
# <a name="data-templates-with-multiple-worksheets"></a>Datamallar med flera kalkylblad

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Hantering av data i appen stöder Microsoft Excel-baserade mallar för datatabeller. Mallarna kan innehålla ett eller flera kalkylblad. Mallar med flera kalkylblad används ofta när det är lämpligt att hantera data i en fil och importera den till flera datatabeller. Ett exempel är platser och lagerställen.

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a>Överför en fil en gång och koppla den till alla entiteter
Låt oss ta ett exempel där det finns en Excel-fil med kalkylblad kallat **Platser** och **Lagerställen**. Om du vill installera dataimportprojektet ska du lägga till den första datatabellen **platser** och överföra filen. Du kan välja **platser** som kalkylblad som ska användas för den här entiteten.

Om du lägger till den andra entiteten **lagerställen** utan att lämna formuläret **Lägg till fil** kommer kalkylbladets sökning låta dig välja kalkylbladet **lagerställen** utan att behöva överföra filen igen. Enda skälet att överföra en ny fil skulle vara om **lagerställen**-data finns i en annan fil.

![Flera kalkylblad.](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a>Korrigera kalkylblad till entitetsmappning

Mappningen av ett kalkylblad till en datatabell i importjobbet kan åtgärdas i rutnätet. Kolumnen **kalkylblad** i rutnätet innehåller kalkylblad från filen som har mappats. Du kan välja ett annat kalkylblad på menyn. Om det valda kalkylbladet redan är mappat till en entitet i projektet data, ber systemet dig att bekräfta ändringen. Vi rekommenderar att du har åtgärdat alla mappningar i rutnätet.

![Uppdatera kalkylbladsmappning.](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a>Mappa till en ny fil

I fall där en ny version av samma fil eller en helt ny fil måste läsas in för befintliga entiteter i ett dataprojekt måste du använda upplevelsen **Lägg till filen** och lägga till entiteterna igen som om de lades till för första gången. Systemet bekräftar att du vill skriva över de befintliga entiteterna i dataprojektet innan du fortsätter. Entiteter som inte läggs till igen (eller över) fortsätter hålla tidigare mappningar från den föregående filen.

## <a name="upload-a-file-using-run-project"></a>Överför en fil genom att använda Kör projekt

Du kan överföra en Excel-fil när du använder alternativet **Köra projekt** som kör ett importprojekt. Du måste vara noga med att överföra filer som har samma kalkylblad som de befintliga mappningarna för datatabellerna i dataprojektet. Om ett kalkylblad inte finns i den nyligen överförda filen, visas ett fel i systemet och importen avbryts. Om mappningen till kalkylbladet måste ändras för en entitet och mappningarna i dataprojektet måste först uppdateras från i inne i dataprojektet innan du använder filen i upplevelsen **Kör projekt**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

