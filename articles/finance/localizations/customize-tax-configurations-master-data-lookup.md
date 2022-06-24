---
title: Anpassa momskonfigurationer för sökning efter huvuddata
description: I den här artikeln beskrivs hur du anpassar momskonfigurationer för att utöka sökfunktionen för huvuddata.
author: kai-cloud
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 31c15c47fa1dc6861ff555a991d5f9233b7df35e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845196"
---
# <a name="customize-tax-configurations-for-master-data-lookup"></a>Anpassa momskonfigurationer för sökning efter huvuddata

[!include [banner](../includes/banner.md)]

Följ stegen i detta avsnitt för att anpassa momskonfigurationer för att utöka sökfunktionen för huvuddata.

## <a name="import-a-tax-configuration-provided-by-microsoft"></a>Importera en momskonfiguration som tillhandahålls av Microsoft

1. I Regulatory Configuration Service (RCS) i arbetsytan för **elektronisk rapportering** väljer du konfigurationsprovider för **Microsoft**.
2. Välj **Databaser**.
3. Markera **Global** och välj sedan **Öppna**.
4. Välj en momskonfiguration, t.ex. **Konfiguration av momsberäkningen**, och välj sedan en version på fliken **Versioner**.
5. Välj **Importera**.

> [!NOTE]
> Modellmappningen Dataverse importeras som standard. Om du får varningsmeddelanden under konfigurationsimporten, ska du aktivera de virtuella enheterna i Dataverse. Mer information finns i [Aktivera Dataverse virtuella entiteter](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="create-a-customized-data-model-configuration"></a>Skapa en anpassad datamodellskonfiguration

1. I arbetsytan **Elektronisk rapportering**, välj **Momskonfigurationer** och välj sedan den datamodellkonfiguration som ska utökas. Välj till exempel **datamodell för momsberäkning**.
2. Välj **Skapa konfiguration**.
3. Välj **Beskattningsbar dokumentmodell härledd från Namn: Datamodell för skatteberäkning, Microsoft**.
4. I fältet **Namn** ange **anpassad datamodell**.
5. Välj **Skapa konfiguration**.

## <a name="create-customized-reference-models"></a>Skapa anpassade referensmodeller

1. På sidan **Momskonfigurationer** väljer du **anpassad datamodell** och sedan **Designer**.
2. Markera knappen med punkter för (**...**) och sedan vyn **Referensmodell**.

    [![Referensmodell.](./media/pic2.png)](./media/pic2.png)

3. Skapa anpassad referensmodell. Den anpassade modellen är en rotmodell. Den anpassade enheten är en postlista. Det anpassade fältet är ett strängfält som du vill använda i söken. Du kan lägga till fler fält efter behov.
4. Markera knappen med punkter för (**...**) och sedan vyn **Beskattningsbart dokument**.
5. Välj det attribut som ska binds till den anpassade referensmodellen. Välj till exempel **anpassade attribut** och gör så här:

    1. Markera **Välj referensmodell**.
    2. Välj **Anpassad modell** och sedan **OK**. Referensmodellnamnet uppdateras till värdet i fältet **naturlig nyckel**.

        [![Välj referensmodelldialogruta.](./media/pic5.png)](./media/pic5.png)

    3. Välj **spara** och välj sedan **slutför**.

## <a name="create-a-customized-model-mapping-configuration"></a>Skapa en anpassad modellmappning konfiguration

1. I arbetsytan **Elektronisk rapportering** välj **Momskonfigurationer** och välj sedan den **Dataverse modellkonfiguration** konfiguration.
2. I fältet **Standard för modellmappning**, välj **Nej**.
3. Välj **Skapa konfiguration**.
4. Välj **Beskattningsbar dokumentmodell härledd från Namn: Dataverse Modellmappning, Microsoft**.
5. I fältet **Namn** ange **Anpassad modellmappning**.
6. I **Målmodell** välj datamodellen **Anpassad datamodell**.
7. Välj **Skapa konfiguration**.

    [![Den nedrullningsbara dialogrutan Skapa konfiguration.](./media/pic6.png)](./media/pic6.png)

8. Välj **Anpassad modellmappning** och ange fältet **Anslutet program** på anslutningen som skapades i steg 8 i [Ställ in en miljö för huvuddatasökning](tax-service-set-up-environment-master-data-lookup.md).
9. Ange fältet **standard för modellmappning** till **Ja**.

## <a name="create-customized-model-mappings"></a>Skapa anpassade modellmappningar

1. På sidan **Momskonfigurationer**, välj **Kartläggning av anpassningsmodeller**.
2. Välj **Designer** och sedan **Anpassningsmodell**.

    [![Anpassningsmodell.](./media/pic8.png)](./media/pic8.png)

## <a name="map-a-model-mapping-to-a-dataverse-entity"></a>Mappa en modellmappning till en Dataverse enhet

1. På sidan **Modellmappningsdesigner** väljer du **Anpassningsmodell** och sedan **Designer**.
2. I trädet **Datakälltyper** välj **Dataverse register**.
3. I fliken **Datakällor** välj **Lägg till rot**.
4. I fältet **Namn** ange **Anpassad Dataverse**.
5. I det andra fältet **Namn**, ange en entitet.
6. Välj **OK**.

    [![Dialogrutan register datakällegenskaper.](./media/pic9.png)](./media/pic9.png)

7. Välj **Anpassad Dataverse** och **Anpassad entitet** och välj **Bind**.

    [![Anpassad Dataverse och Anpassad entitetsbindning.](./media/pic10.png)](./media/pic10.png)

8. Under **Anpassad Dataverse** och **Anpassat fält** välj ett fält och sedan **Bind**.

    [![Anpassad Dataverse och Anpassad fältbindning.](./media/pic11.png)](./media/pic11.png)

9. Välj **spara** och välj sedan **slutför**.

## <a name="create-a-customized-tax-configuration"></a>Skapa en anpassad momskonfiguration

1. I arbetsytan **Elektronisk rapportering** välj **Momskonfigurationer** och välj sedan den **Momsberäkningskonfiguration**.
2. Välj **Skapa konfiguration**.
3. Välj **Momstjänstkonfiguration härledd från Namn: Momsberäkningskonfiguration, Microsoft**.
4. I fältet **Namn** ange **Anpassad konfiguration**.
5. Välj **Skapa konfiguration**.
6. Välj **Anpassad konfiguration** och sedan **Designer**.
7. I fältet **Datamodell**, välj **Anpassad datamodell**.
8. I fältet **Datamodellversion**,välj motsvarande version av datamodellen.

    [![Val av egenskaper.](./media/pic13.png)](./media/pic13.png)

9. Välj **Slutför**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
