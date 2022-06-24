---
title: Anskaffnings- och källparametrar för hemtagningskostnad
description: Denna artikel beskriver hur du konfigurerar relevanta parametrar för Anskaffning och inköp när du använder modulen Hemtagningskostnad.
author: Weijiesa
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 92ce3e3d09bed15970375735f680b1b8348bbca8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905991"
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
