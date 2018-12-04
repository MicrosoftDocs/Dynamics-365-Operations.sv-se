---
title: "Konfigurera ett lagerställe med hjälp av en konfigurationsmall"
description: "Det här avsnittet innehåller information om hur du konfigurera ett lagerställe med hjälp av en konfigurationsmall."
author: perlynne
manager: AnnBe
ms.date: 11/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DataManagementWorkspace, DMFQuickImportExportEnhanced, DMFDefinitionGroupTemplate, DMFEntityTemplateDefinitionLoadDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 83648a93f367510d7b04bbd04a9f37689ecfaa59
ms.openlocfilehash: e952a2f988645ccff7617817262cbf0e90bfd8ab
ms.contentlocale: sv-se
ms.lasthandoff: 05/23/2018

---

# <a name="set-up-a-warehouse-by-using-a-warehouse-configuration-template"></a>Konfigurera ett lagerställe med hjälp av en konfigurationsmall

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om hur du konfigurera ett lagerställe med hjälp av en konfigurationsmall. Det finns flera fördefinierade konfigurationsmallar som du kan använda. Information om hur du använder dessa mallar finns i [Konfigurationsdatamallar](../../dev-itpro/data-entities/configuration-data-templates.md).

## <a name="scenarios-where-configuration-templates-can-be-helpful"></a>Scenarier där konfigurationsmallar kan vara till hjälp

Konfigurationsmallar kan vara användbar i många situationer. Nedan följer några exempel:

- Du har slutfört och testat en konfigurationsinställning i en testmiljö och nu vill du kopiera inställningen till en produktionsmiljö.
- Du vill distribuera lagerstyrningsinställningar för flera juridiska personer eller skapa ett nytt lagerställe i samma juridiska person.
- Du vill snabbt förbereda dig för en demonstration av funktionerna för lagerstället.
- Du vill att befintliga objekt och lager ska använda funktionerna i lagerstyrning i stället för funktionen i Lagerhantering.

I det här avsnittet gäller det första av dessa scenarier. Det visar hur du kan använda en konfigurationsmall för att kopiera en konfigurationsinställning från en testmiljö till en produktionsmiljö.

## <a name="copy-a-configuration-setup-from-a-test-environment-to-a-production-environment"></a>Kopiera en konfigurationsinställning från en testmiljö till en produktionsmiljö

För det här scenariot existerar redan konfigurationsinställningarna för ett lagerställe och vissa transaktionsprocesser finns redan i en testmiljö. Du vill nu kopiera konfigurationsinställningarna för lagerstället från testmiljön till en produktionsmiljö.

> [!NOTE]
> Det är viktigt att du inkluderar andra inställningsdata när du kopierar en konfigurationsinställning. Du vill till exempel ställa in produkter genom att kopiera inställningarna från en testmiljö. Men du kan inte ställa in en fast plockplats för en produkt innan den produkten skapas. Även om enskilda konfigurationsmallar inte stöder den här typen av beroenden, finns det standarddatamallar som stöder den. Du kan enkelt inkludera dessa standarddatamallar i konfigureringsprocessen.

### <a name="export-a-default-warehouse-template"></a>Exportera en standardlagermall 

1. Öppna arbetsytan **Datahantering**.

    > [!NOTE]
    > Om du använder den här arbetsytan för första gången måste du läsa in alla dataetabellerna innan du fortsätter.

2. Välj panelen **mallar** och markera sedan **läsa in standardmallar** för att läsa in standardmallarna.

    > [!NOTE]
    > **Läsa in standardmallar** är endast tillgängligt i vyn **utökat**. Välj **ramverksparametrar** och sedan, i vyn **Visa standard** väljer du **utökad vy**.

3. När standardmallarna läses in kan du ändra dem så att de uppfyller dina affärsbehov.

    > [!NOTE]
    > Om du vill läsa in standardmallar och importera mallar måste du ha systemadministratörsbehörighet. Detta krav bidrar till att garantera att alla enheter läses in korrekt i mallen.

4. Kontrollera att du är i den juridiska persona som du vill exportera företagsspecifika data från.
5. Markera **exportera** i arbetsytan.
6. Skapa ett nytt exportprojekt.
7. Välj **+ Lägg till mall** och hitta **400 - Lagerstyrningssystem** standardmall för lagerstället. Den här mallen lägger till datatabeller för lagerkonfiguration.

    > [!NOTE]
    > Om den data du vill exportera måste filtreras (om du till exempel vill exportera data som hör till ett visst lagerställe), måste du utvärdera varje datatabell och lägga till filtrering via en fråga. Alternativt kan du exportera alla data och ta bort de poster som inte krävs i målfilerna.

8. Välj **Exportera**. Data som är relaterad till alla datatabellerna i projektet exporteras.

Du kan hämta en zip-fil för datapaketet. Den här filen innehåller alla data i det markerade formatet (till exempel Excel-format). Som tidigare nämnts, kanske några av posterna i datapaketfilerna behöver uppdateras innan du kan importera dem till produktionsmiljön. Kontrollera att du inte ändrar filnamnet om du uppdaterar en post.

### <a name="import-a-warehouse-configuration-setup"></a>Importera en konfiguration för lagerställe

1. I målmiljön ser du till att du är i företaget som du vill importera lagerställets data till.

    > [!NOTE]
    > Identifiera eventuella databeroenden innan du utför importen. Till exempel mallen **lagerstyrning** innehåller en datatabell som heter **lagerdispositionskoder**. Entiteten innehåller data som hör till installationssidan **dispositionskoder** (**lagerstyrning** > **inställningar** > **mobiltelefon** > **dispositionskoder**). Om en befintlig installation redan hanterar returprocess för försäljningsorder, innehåller fältet **returdispositionskod** ett värde. Dispositionskoden i det här fältet hör till datatabellen **dispositionskod** som är en del av mallen **försäljning och marknadsföring**. Om data från datatabellen **dispositionskod** inte importeras före data från fältet **lagerdispositionskoder** misslyckas importen.

2. I arbetsytan **datahantering**, välj **Import**.
3. Skapa ett nytt importprojekt.
4. Välj **+ Lägg till fil** och överför zip-filen för datapaketet.
5. Välj **Importera**. I vyn **utökat** kan du använda alternativet **Filter** för att snabbt få en översikt över problem som kan uppstå under importen.

Loggen **Visa körning** ger detaljerad information om varje dataenhet som importeras. Du kan använda mellanlagringsdatavyn för att snabbt komma till måldata. På så sätt visas hur de importerade data ser ut på tillhörande sidor i programmet. När du använder standarddatamallar fungerar importsekvensen för varje datatabell på fördefinierade sätt, för att garantera att alla beroende data importeras först. Om anpassade datatabeller ingår i projektet, måste du kontrollera att du angett rätt sekvens. Mer information finns i [Konfigurationsdatamallar](../../dev-itpro/data-entities/configuration-data-templates.md).

Om du vill veta mer om hur du använder lagermall för att kopiera konfigurationen för ett lagerställe från ett företag till ett nytt företag inom samma instans kan du se den här 3 minuters videon på YouTube: [Använd lagermall för att kopiera konfigurationen i Microsoft Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=K2WIfFlqJYs).

## <a name="related-topic"></a>Relaterat ämne

[Konfigurationsdatamallar](../../dev-itpro/data-entities/configuration-data-templates.md)

