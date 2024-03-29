---
title: Företagsövergripande datakällor i elektronisk rapportering (ER)
description: Den här artikeln beskriver hur du kan använda datakällor mellan företag i elektronisk rapportering (ER).
author: kfend
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.form: ERModelMappingDesigner, ERFormatMappingLegalEntityFilterTable
ms.openlocfilehash: ec96533dd2da933d5275adadedc9a92a33e47a38
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277739"
---
# <a name="cross-company-data-sources-in-electronic-reporting-er"></a>Företagsövergripande datakällor i elektronisk rapportering (ER)

[!include[banner](../includes/banner.md)]

Du kan utforma elektronisk rapportering (ER)-format som skapar utgående dokument i olika format. När ett dokument skapas anropar ett ER-format datakällor som har konfigurerats i en motsvarande ER-modellmappning. Om du vill konfigurera åtkomst till programregister för att hämta poster kan du använda ER-datakällor av typen **Registerposter**. När åtkomst till registret är ett delat register (det vill säga ett register där data sparas utan företags-ID), returnerar denna datakälla alla poster. När åtkomst till registret är ett företagsberoende register (det vill säga en tabell där data sparas per företag) returnerar denna data enbart de poster som har sparats för det aktuella företaget (det vill säga företagssammanhanget som ER-formatet körs under).

Varje datakälla av typen **Registerposter** i en modellmappning kan nu markeras som ett korsföretags datakälla. Därför kan du använda datakällor av typen **Registerposter** för att få tillgång till data mellan företag i programregistren.

Om du markerar en datakälla som mellan företag händer följande:

- För en datakälla som refererar till alla delade register utom CompanyInfo returnerar datakällan alla poster som finns i den hänvisade tabellen. 
- För en datakälla som hänvisar till registret CompanyInfo, även om CompanyInfo är ett delat register returnerar datakällan poster som innehåller ID för ett företag från det definierade området.
- För alla företagsberoende register returnerar datakällan poster av den hänvisade tabellen med ID för ett företag från det definierade området.

I dialogrutan systemfråga när alternativet **Fråga efter fråga** aktiveras för alla datakällor som har markerats som mellan företag kan du manuellt välja ett eller flera företag som ska inkluderas i fliken **Företagsintervall**.

> [!IMPORTANT]
> Precis som andra filter sparas företagsfiltret som senast använda värde för frågor när du kör ett ER-format. Filtret ändras inte automatiskt om du ändrar värdet för en datakälla mellan företag. Ta bort motsvarande användarspecifika val om du vill använda ett annat värde mellan företag på en annan datakälla.

Du kan välja de poster som är markerade som mellan företa för varje datakälla genom att använda funktionerna **FILTER** och **WHERE** i ER uttryck. Fältet **dataAreaID** kan också användas som en företagsidentifierare. För närvarande är fältet **dataAreaID** begränsat till följande typer av villkor när funktionen **FILTER** används:

- Endast villkor som har en enda fältjämförelse för **dataAreaID** stöds.
- Endast jämförelser som innehåller uttryck som inte beror på postlisteartiklar tillåts.

Därför är följande uttryck giltiga.

```ER Expression
FILTER (MyTable, MyTable.dataAreaID = $StringUserInputParameter)
While shown below expressions will not pass the validation:
FILTER (MyTable, MyTable.dataAreaID = MyTable2RecordsList.MyField)
FILTER (MyTable, 
    OR(
        MyTable.dataAreaID = $StringUserInputParameter1,
        MyTable.dataAreaID = $StringUserInputParameter2
    )
)
```

Området inkluderar som standard alla företag i det aktuella programmet. Detta kan dock begränsas. Om du vill begränsa omfattningen av dataåtkomst mellan företag för ett enda ER-format, tilldela en viss organisationshierarki till formatet. När en hierarki definierats för ett ER-format, endast poster för juridiska personer som presenteras i den tilldelade hierarkin returneras, även om formatet anropar datakällor mellan företag. När en referens till en hierarki som inte längre existerar definieras för ett ER-format tillämpas standardomfånget och formatet anropar datakällor mellan företag. I denna situation returneras poster för alla programföretag.

Observera att om alternativet **använd utkast** aktiveras för den som tilldelats till en organisationshierarki med ett enda ER-format kommer juridiska personer från hierarkins utkastversion att användas för att identifiera omfattningen för datakällor mellan företag. Om utkastsversionen inte existerar används juridiska personer från den senast publicerade versionen av det här organisationshierarkin för detta.

Observera att om alternativet **använd utkast** avaktiveras för den som tilldelats till en organisationshierarki med ett enda ER-format kommer juridiska personer från organisationshierarkins senast publicerade version att användas för att identifiera omfattningen för datakällor mellan företag. Datumeffektivitet för organisationshierarkier stöds inte ännu i ER-ramverket.

Hierarkin kan tilldelas ett format på en viss sida som kan nås från ER-arbetsytan eller med hjälp av menyalternativen **Organisationsadministration \> Elektronisk rapportering \> Filter för juridisk person för format**. För åtkomst till sidan måste behörigheten **Hantera filter för juridisk person för format** (ERMaintainFormatMappingLegalEntityFilters) tilldelas en användare. Begränsning av omfattningen för hierarkibaserade jurdiska personer för formatet används tillsammans med begränsningen att användaren kan ange manuellt i dialogrutan systemfråga. Skärningspunkten mellan dessa begränsningar används när formatet körs.

Om du vill veta mer om den här funktionen spelar du upp arbetsguiden **ER-åtkomstregistreringar av företagsberoende tabeller i läget mellan företag**, som är en del av affärsprocessen 7.5.4.3 Skaffa/utveckla komponenter för IT-tjänster eller IT-lösningar (10677) och kan hämtas från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Den här uppgiftsguiden guidar dig genom processen att konfigurera en ER-modellmappning och ER-format för att komma åt programregister i läget mellan företag.

Hämta följande filer för att slutföra uppgiftsguiden:

- [Konfiguration av ER-datamodell – CrossCompanyDataAccessModel.xml](https://download.microsoft.com/download/4/2/5/4258f891-7054-4821-aedd-3721ba25fdd5/CrossCompanyDataAccessModel.xml)
- [ER-formatkonfiguration – CrossCompanyDataAccessFormat.xml](https://download.microsoft.com/download/3/2/1/321deb75-3ba9-4323-99bf-207a52c60b5c/CrossCompanyDataAccessFormat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
