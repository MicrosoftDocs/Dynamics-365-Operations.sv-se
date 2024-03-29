---
title: Modul för ordersökning
description: Denna artikel avhandlar modulen för ordersökning och förklarar hur du konfigurerar den i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: a891de4a1da6641a02b8316d16ac2e9a8180fac1
ms.sourcegitcommit: e25fe4228add88dd37f4f38ece86979e1c621f6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2022
ms.locfileid: "9734262"
---
# <a name="order-lookup-module"></a>Modul för ordersökning

[!include [banner](includes/banner.md)]

Denna artikel avhandlar modulen för ordersökning och förklarar hur du konfigurerar den i Microsoft Dynamics 365 Commerce.

I modulen för ordersökning ges ett formulär som kunderna kan använda när de söker efter order som de har lagt på en näthandelsplats. Den används i funktionen [Aktivera ordersökning för gästkassor](order-lookup-guest.md). Sökmodulen för order kan användas för att slå upp order som har skickats via en näthandelsplats, butikskassan (POS) eller ett kundtjänstcenter. Formuläret kan hämta order som skickats både av gästanvändare och av registrerade användare.

I bilden nedan visas ett exempel på det formulär som återges av modulen för ordersökning. När kunder fyller i formuläret och väljer **Sök efter din order** omdirigeras de till sidan med orderdetaljer.

![Formulär för modulen för ordersökning på en sida.](./media/OrderLookup_module.PNG)

## <a name="order-lookup-module-properties"></a>Egenskaper för modulen för ordersökning

| Egenskapsnamn     | Värde     | beskrivning |
|-------------------|-----------|-------------|
| Rubrik           | Text      | Rubriken som visas högst upp i formuläret (till exempel "Sök efter ordern"). |
| RTF-format         | RTF-format | Valfri förklarande text som visas under rubriken. |
| Typ av orderstatus | Uppräkning      | <p>Välj den typ av information som formuläret kommer att begära av kunden utöver orderbekräftelse-ID:t. Följande värden stöds nu:</p><ul><li><b>E-post</b> – Formuläret kommer att innehålla ett fält där kunder kan ange den e-postadress som de använde när de lade ordern.</li><li><b>Ingen</b> – Formuläret begär ingen information förutom orderbekräftelse-ID:t.</li></ul> |

## <a name="add-an-order-lookup-module-to-a-page"></a>Lägg till modulen för ordersökning på en sida

Modulen för ordersökning kan läggas till på valfri sida på näthandelsplatsen. Om du vill använda modulen för ordersökning för att aktivera ordersökning för gästkassor, se till att lägga till den på en sida som inte kräver att användaren är inloggad. Om du vill söka efter en sidas inställning **Kräver inloggning?** i Commerce-webbplatsbyggarens trädvy väljer du platsen **Standardsida (obligatorisk)** och tittar längst ned i den högra rutan.


> [!NOTE]
> Om du vill aktivera order sökfunktionen måste nyckeln **Offerter** vara aktiverad under **Licenskonfiguration** > **Konfigurationsnycklar**.
>
> ![Licensnyckeln för offerter måste ha aktiverats](./media/Quotations_License_Key_Configuration.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Aktivera ordersökning för gästkassor](order-lookup-guest.md)

[Modulbibliotek – översikt](starter-kit-overview.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
