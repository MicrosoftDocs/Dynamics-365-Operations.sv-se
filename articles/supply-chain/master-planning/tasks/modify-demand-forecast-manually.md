---
title: 'Guide: Ändra en efterfrågeprognos manuellt'
description: Detta ämne beskriver hur du ändrar prognosen för en artikel
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83575da4d382743b45c2de7964a7cbf1cc366989955884100dcb766a67166cf1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741295"
---
# <a name="guide-modify-a-demand-forecast-manually"></a>Guide: Ändra en efterfrågeprognos manuellt

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ändrar prognosen för en artikel. Den här proceduren är avsedd för produktionsplaneraren.

## <a name="modify-the-forecast-for-a-selected-item"></a>Ändra en prognosen för en vald artikel

För att ändra prognosen för en vald artikel:

1. Gå till **Moduler \> Hantering av produktinformation \> Produkter \> Frisläppta produkter**.
1. Hitta och markera önskad post i listan. Välj den artikel om du vill ändra prognosen för.
1. I åtgärdsfönstret öppnar du fliken **Plan** och väljer **Efterfrågeprognos**.
1. Välj en rad i listan. Om det inte finns några prognosrader skapar du en ny rad genom att välja **Ny** i åtgärdsfönstret.  
1. I fältet **Försäljningskvantitet** anger du ett positivt värde. Det här numret representerar den prognosticerade kvantiteten för artikeln. Ett fel visas om du anger ett negativt tal.
1. Fyll i övriga fält efter behov.
1. Välj **Spara** i åtgärdsfönstret.

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a>Ändra prognosen för en eller flera artiklar med Microsoft Excel

För att ändra prognosen för en eller flera artiklar med Microsoft Excel:

1. Gör något av följande:
    - Öppna sidan **Efterfrågeprognos** för valfri artikel (det spelar ingen roll vilken) som beskrivs i föregående avsnitt.
    - Gå till **Huvudplanering \> Prognosticering \> Manuell prognosangivelse \> Rader för efterfrågeprognos**.
1. I åtgärdsfönstret väljer du **Öppna i Microsoft Office \> Poster för efterfrågeprognos**.
1. Välj en hämtningsplats, spara och öppna sedan den hämtade filen i Excel.
1. Om en varning visas väljer du **Aktivera redigering**.
1. Logga in i Supply Chain Management med hjälp av Microsoft Dynamics-åtgärdsfönstret. Du måste logga in med alternativet **Håll mig inloggad** aktiverat, och du måste lita på programmet för dataanslutning.
1. I Excel-kalkylbladet visas nu alla aktuella rader i efterfrågeprognosen för ditt företag.  Lägg till, ta bort och redigera efterfrågeprognosrader efter behov.
1. Välj **Publicera** i Microsoft Dynamics-åtgärdsfönstret om du vill föra över ändringarna tillbaka till Supply Chain Management.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
