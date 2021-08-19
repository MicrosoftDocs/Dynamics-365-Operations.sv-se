---
title: Anskaffnings- och källparametrar för hemtagningskostnad
description: Det här ämnet beskriver hur du ställer in relevanta parametrar för Anskaffning och inköp när du använder modulen hemtagningskostnad.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d8aa7e6ebd254289df410814a08a5d0fe31239dd103cb428f0d4bc401fbfb28a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747947"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a>Anskaffnings- och källparametrar för hemtagningskostnad

[!include [banner](../../includes/banner.md)]

Sidan **Anskaffnings- och inköpsparametrar** har några inställningar som är särskilt relevanta när du använder modulen **Hemtagningskostnad**. Använd dialogrutan **Uppdatera orderrader** som öppnas från sidan **Anskaffnings- och källparametrar** om du vill ange om inköpsorderrader ska uppdateras automatiskt när ändringar görs i inköpsorderrubriken.

Om du vill slutföra denna inställning, följ dessa steg.

1. Gå till **Anskaffning och källa \> Inställningar \> Anskaffnings- och källparametrar**.
1. På fliken **Allmänt**, välj länken **Uppdatera orderrader**.
1. Dialogrutan **Uppdatera orderrader** visar fälten i orderrubriken som också kan tillämpa automatiska uppdateringar på relaterade fält på orderraderna. Ställ in varje fält i listan på ett av följande värden:

    - **Alltid** – Orderraderna uppdateras automatiskt när orderrubriken uppdateras.
    - **Aldrig** – Orderraderna uppdateras aldrig när orderrubriken uppdateras.
    - **Uppmaning** – Användaren uppmanas att välja om orderraderna ska uppdateras.
