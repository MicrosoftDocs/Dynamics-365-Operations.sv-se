---
title: Skapa en ny funktion för elektronisk fakturering
description: I det här avsnittet beskrivs hur du skapar en ny funktion för elektronisk fakturering när det inte finns någon konfigurerbar funktion för ditt land eller din region i rutan.
author: gionoder
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ffef49c78fd0564db7a2329580ad33a9ccc633c8ac74557e625d1cfb29931576
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744945"
---
# <a name="create-a-new-electronic-invoicing-feature"></a>Skapa en ny funktion för elektronisk fakturering

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en ny funktion för elektronisk fakturering när det inte finns någon konfigurerbar funktion för ditt land eller din region i rutan.

Följ de här stegen om du vill skapa en ny funktion för e-fakturering:

1. Skapa en ny konfiguration av filformatet genom att använda fakturamodellkonfigurationen som finns och dra nytta av den befintliga fakturamappningen för funktionen du vill skapa.
2. Lägg till filformatskonfigurationer till konfigurationerna för elektronisk fakturering.
3. Skapa inställning av funktionen e-fakturering.
4. Slutför den nya funktionen för elektronisk fakturering och publicera den i den globala databasen för din organisation.
5. Distribuera den nya funktionen elektronisk fakturering till tjänstemiljö.

## <a name="create-new-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Skapa nya filformatskonfigurationer som härleds från den befintliga fakturamodellen

I den här proceduren skapar du de filformatskonfigurationer som krävs för den nya funktion för elektronisk fakturering som du vill skapa. Du kan skapa den elektroniska fakturafilformatskonfigurationen och alla andra filformatskonfigurationer som din nya funktion för elektronisk fakturering kan kräva.

Innan du börjar med proceduren måste du logga in på kontot Regulatory Configuration Service (RCS).

1. I Microsoft Dynamics 365 Finance, i arbetsytan **elektronisk rapportering**, välj **Databaser** för konfigurationsleverantören **Microsoft**.
2. Välj **Global**, välj **Öppen** och välj sedan i den vänstra rutan **Fakturamodell** konfiguration.

    > [!IMPORTANT]
    > För Brasilien väljer du i stället modellkonfigurationen för **skattedokument**.

3. Välj **Konfigurationer** på fliken **Importera**.
4. Stäng sidan.
5. Stäng sidan.
6. Markera **konfigurationen Rapporter** och välj sedan den fakturamodell som du importerat.
7. Välj **Skapa konfiguration** och välj sedan **Format baserat på fakturakontextmodellen**. 
8. Ange ett namn och en beskrivning för formatkonfiguration.
9. I fältet **Formattyp** ska du välja filtilläggstyp..
10. Välj **Skapa konfiguration** och välj sedan formatkonfigurationen som du skapade.
11. Välj **Designer** och använd verktyget Formatdesigner när du vill konfigurera fillayouten så att den uppfyller specifikationerna för filformatet.
12. Stäng sidan.
13. På snabbfliken **Versioner**, välj **ändra status** \> **slutförd**.
14. Välj **Ändra status** \> **Dela** för att publicera formatkonfigurationen till Global databasen.

Den nya konfigurationen för filformatet måste delas med Microsoft-domänen innan konfigurationen kan förbrukas av den elektroniska faktureringstjänsten.

1. Välj den formatkonfiguration som du arbetar på. Konfigurationens status måste vara **Delad**.
2. Välj global **Versioner**, välj **Avancerad delning** \> **Global databas**.
3. I fliken **Delas med** väljer du **Organisation**.
4. I fältet **Parametrar** ange **Microsoft.com** för att formatkonfigurationen med Microsoft-domänen.
5. Välj **OK**.

## <a name="create-the-new-electronic-invoicing-feature"></a>Skapa en ny funktion för elektronisk fakturering

1. I RCS arbetsytan **globaliseringsfunktioner** i avsnittet **Funktioner**, välj panelen **Elektronisk faktura**.
2. Välj **Lägg till** och sedan **Ny funktion**.
3. Ange ett namn och en beskrivning för funktionen Elektronisk fakturering.
4. Välj **skapa funktion**.

## <a name="add-electronic-invoicing-feature-configurations"></a>Lägga till konfigurationer för funktionen för e-fakturering

1. Välj den funktion för elektronisk fakturering som du arbetar med.
2. Välj **Konfigurationer** på fliken **Lägg till**.
3. I rutan **Konfigurationer**, bläddra och välj de filformatskonfigurationer som din elektroniska fakturafunktion kräver för att generera den elektroniska fakturafilen.
4. Välj **OK**.

## <a name="add-electronic-invoicing-feature-setups"></a>Lägga till konfigurationer för funktionen för e-fakturering

1. På fliken **Inställningar**, välj **Lägg till** och välj **Anpassade inställningar**.
2. Ange ett namn och en beskrivning för funktionsinställningen.
3. I fältet **Inställningstyp**, välj **Bearbetning pipeline**.
4. Markera **Skapa**.
5. Välj den inställning du arbetar med och välj sedan **Redigera**.
6. På fliken **Bearbetning av pipeline** välj **Ny** för att lägga till åtgärden pipeline. Mer information om pipelines finns i [Åtgärder](e-invoicing-configuration-rcs.md#actions).
7. På fliken **tillämplighetsregler**, välj **Ny** för att lägga till tillämplighetsreglerna. Mer information om tillämplighetsreglerna finns i [tillämplighetsreglerna](e-invoicing-configuration-rcs.md#applicability-rules).
8. På fliken **Variabler**, välj **Ny** om du vill lägga till variabler.
9. Välj **Spara** och välj sedan **Validera** om du vill kontrollera konfigurationens överensstämmelse.
10. Stäng sidan.

## <a name="deploy-the-electronic-invoicing-feature-to-the-service-environment"></a>Distribuera funktionen elektronisk fakturering till tjänstemiljö

Information om hur du utför den här uppgiften finns i [Distribuera den elektroniska faktureringsfunktionen i tjänstemiljön](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="deploy-the-electronic-invoicing-feature-to-a-connected-application"></a>Distribuera funktionen elektronisk fakturering till anslutet program

Mer information om hur du utför den här uppgiften finns i [Konfigurera programinställningarna](e-invoicing-get-started.md#configure-the-application-setup) och distribuera den elektroniska [faktureringsfunktionen till det kopplade programmet](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application).
