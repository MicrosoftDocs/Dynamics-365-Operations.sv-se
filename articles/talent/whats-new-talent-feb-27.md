---
title: Nyheter och ändringar i Dynamics 365 Talent (27 februari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f175c6e60cf87c7dcbde0eaf35357130fa035712
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024009"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-27-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (27 februari 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2163

### <a name="add-a-custom-fields-menu-item-to-system-administration"></a>Lägga till ett menyalternativ för anpassat fält till systemadministration

Navigera till menyn **anpassade fält** har lagts till i arbetsytan **systemadministration**.

### <a name="hide-the-import-and-create-options-for-new-mobile-applications"></a>Dölj importen och skapa alternativ för nya mobila program

För närvarande går det inte att skapa nya mobilappar i Talent. Alternativet för att skapa nya mobila funktioner har tagits bort från menyn **Mobilapp**.

### <a name="variable-compensation-award-dmf-entity"></a>Belöningar för rörlig kompensation (DMF-entitet)

I den här versionen är nu **Belöningar för rörlig kompensation**, entiteten Data Management Framework (DMF) nu tillgänglig för export.

### <a name="uk-addresses-appear-in-the-personnel-management-analytics-page-as-swiss-addresses"></a>Adresser för Storbritannien visas på sidan för analys av personalhantering som schweiziska adresser

I den här versionen visas adresser efter ort. Den här versionen korrigerar problem där visualiseringar förvrängde bilden av en medarbetares plats.

### <a name="the-workforce-power-bi-report-shows-an-error-when-a-workers-seniority-date-is-on-leap-day"></a>Personalens Power BI-rapport visar fel när datum för tjänsteålder för arbetaren är en skottdag

En korrigering har gjorts i Microsoft Power BI för att ta hänsyn till datum för tjänsteålder som infaller den 29 februari.

### <a name="employee-fixed-compensation-employee-variable-awards-employee-variable-plans-enrollments-allow-for-custom-fields"></a>Medarbetarens fasta kompensation, medarbetarens rörliga belöningar, medarbetarens rörliga planer (registreringar) tillåter anpassade fält

Anpassade fält kan nu läggas till för medarbetarens fasta kompensation, medarbetares rörliga belöningar och medarbetares rörliga planer (registreringar). Du kan nu söka efter mer information om medarbetarens fasta och rörliga kompensationsplaner utöver de uppgifter som är tillgängliga som standard. Anpassade fält kan anges och uppdateras via användargränssnittet eller de entiteter som finns.

### <a name="other-miscellaneous-bug-fixes"></a>Diverse andra felkorrigeringar

Den här versionen innehåller andra mindre felkorrigeringar.

## <a name="coming-soon"></a>Kommer snart

### <a name="advanced-compensation-security-fixed-and-variable"></a>Avancerad kompensationssäkerhet (fasta och rörliga)

I många organisationer kan kompensationer och förmåner chefer bara har tillgång till specifika kompensationsposter. Posterna kan vara för chefer eller nationella medarbetare. Den här ändringen låter personalen (HR) hantera och underhålla kompensationsplaner för olika medarbetare i organisationen. Säkerhetsroller som kan tilldelas fasta och variabla planer bestämmer åtkomsten till dessa planer och medarbetardata som är relaterade till dem (till exempel löneinformation och bonusposter). Endast roller med angiven åtkomst ska kunna bearbeta kompensation för dessa anställda.

### <a name="platform-update-24-for-finance-and-operations"></a>Plattformsuppdatering 24 för Finance and Operations

Mer information om plattformsuppdatering 24 för Microsoft Dynamics 365 Finance and Operations plattformsuppdatering 24 (mars 2019) finns i [Förhandsgranskningsfunktioner i Finance and Operations plattformsuppdatering 24 (mars 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).

### <a name="make-employee-fixed-compensation-available-for-future-position-assignments"></a>Gör medarbetarens fasta kompensation tillgänglig för framtida befattningstilldelningar

Detta gäller för medarbetare som ansluter sig till en organisation med startdatum i framtiden. Denna ändring tillåter definition av fast kompensation för anställda med framtida befattningstilldelningar.

## <a name="known-issues"></a>Kända problem

### <a name="changes-to-the-core-hr-integration-template-talent-common-data-service-to-finance"></a>Ändringar i Core HR-integrationsmall (Talent Common Data Service till Finance)
Mallen för Core HR har uppdaterats till en ”avancerad frågemall”. Därför blir avancerad fråga som standard tillgänglig för projekt som har skapats med hjälp av den här mallen. Dessutom visas alla standardmappningsfunktioner bara i redigeraren för avancerad fråga. (Standardmappningsfunktioner visas som ”FN” i mappningarna.)

Mer information om mappningsfel finns i [Nyheter eller ändringar i Dynamics 365 Talent: Core HR (14 december 2018)](https://docs.microsoft.com/dynamics365/unified-operations/talent/whats-new-talent-december-14).

Om du vill använda den nya mallen skapar du ett nytt projekt och väljer den nya Talent integrationsmallen.

Följ dessa steg om du vill uppdatera den befintliga mallen.

1. Uppdatera följande mappningar:

    - **Jobbefattningar till befattningar:** ta bort den här mappningen.
    - **Jobbefattningar till befattningars överordnade jobbtilldelningar:** ta bort den här mappningen.
    - **Jobbefattningar till jobb till grundläggande befattning:** lägga till en ny mappning från entiteten **Jobbefattningar**Common Data Service till entiteten **grundläggande befattning** Finance and Operations. Flytta till position 7 i sekvensen.

        [![Jobbefattningar till grundläggande beffattningsmappning](./media/CDS-Mapping1.png)](./media/CDS-Mapping1.png)

    - **Jobbefattningar till befattningsdetaljer:** lägga till en ny mappning från entiteten **Jobbefattningar**Common Data Service till entiteten **befattningsdetaljer** Finance and Operations. Flytta till position 8 i sekvensen.

        [![Jobbefattningar till befattningsdetaljmappning](./media/CDS-Mapping2.png)](./media/CDS-Mapping2.png)

    - **Jobbefattningar till befattningstidslängder:** lägga till en ny mappning från entiteten **Jobbefattningar**Common Data Service till entiteten **befattningstidslängder** Finance and Operations.

        [![Jobbefattningar till befattningstidslängdmappning](./media/CDS-Mapping3.png)](./media/CDS-Mapping3.png)

    - **Jobbefattningar till befattningshierarkier:** lägga till en ny mappning från entiteten **Jobbefattningar**Common Data Service till entiteten **befattningshierarkier** Finance and Operations. Välj **avancerad fråga** för att göra en avancerad fråga tillgänglig för projektet.

       [![Knappen Avancerad sökfråga](./media/CDS-Advanced-Query.png)](./media/CDS-Advanced-Query.png)

2. Lägg till följande mappningar.
    
    [![Mappning](./media/CDS-Mapping4.png)](./media/CDS-Mapping4.png)

    1. cdm_jobpositionnumber cdm_jobspositionnumb... = POSITIONID cdm_parentjobpositionid.cdm-jobpositionnumb... = PARENTPOSITIONID cdm_validfrom cdm_validfrom = VALIDFROM cdm_validto cdm_validto = VALIDTO
       
    2. Välj länken **Avancerad fråga och filtrering** bredvid fältet **Sök**.  

    3. Hitta kolumnen **cdm_parentjobpositionid.cdm_jobpositionnumber** och välj knappen med nedpilen till höger.

    4. I dialogrutan som visas väljer du **ta bort tomma**.

    5. Välj **Lägg till kolumn \> Lägg till villkorlig kolumn** för att lägga till en standardvärdetransformering för HIERARCHYTYPENAME.

        [![Lägg till kommando för villkorlig kolumn](./media/Add-column.png)](./media/Add-column.png)

    6. I dialogrutan **Lägg till villkorlig kolumn** anger du **HIERARCHYTYPENAME** som namnet på den nya kolumnen.
    7. I delen av villkoret **om** markerar du ett fält genom att använda **lika med** som relationen och anger något värde. I delar av villkoret ***sedan** och **annars** anger du vad som ska utgöra standardvärdet. I det här fallet anger du **rad** i båda delarna.

        [![Lägg till villkorsstyrd kolumndialogruta](./media/Add-conditional-column.png)](./media/Add-conditional-column.png)

    8. Välj **OK** för att stänga dialogrutan **Avancerad fråga och filtrering**.
    9. På sidan **mappningsuppgift** väljer du den nya kolumnen som källa för att skapa en annan mappning för HIERARCHYTYPENAME.

        [![Mappning](./media/CDS-Mapping5.png)](./media/CDS-Mapping5.png)
