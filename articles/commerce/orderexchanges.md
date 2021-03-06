---
title: Konfigurera och behandla ett utbyte för en returorder
description: I detta avsnitt beskriver vi hur du konfigurerar ett utbyte för en returorder i Dynamics 365 Commerce.
author: josaw1
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 46d6e912aca64951da2865f5609a9dc22fbbcbe3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804611"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Konfigurera och behandla ett utbyte för en returorder

[!include [banner](includes/banner.md)]

I tidigare versioner av Dynamics 365 Commerce behandlades returer mot en kundorder genom att returorderdokumentet i Headquarters användes. Returorderdokumentet går dock att använda för att enbart behandla produkter som returneras. De returnerade produkterna anges med en negativ kvantitet på returorderraderna. Försäljningar anges med en positiv kvantitet. Returorderdokumentet stöder emellertid inte positiva kvantiteter. Tidigare versioner av appen stödde på grund av denna begränsning inte scenarier där produktbyten gjordes med hjälp av returorderdokumentet.

Denna funktion har dock lagts till så att det ska gå att byta ut produkter på returorder. Commerce använder nu försäljningsorderdokumentet i stället för returorderdokumentet för att bearbeta dessa typer av transaktioner.

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>Konfigurera Commerce för att stödja utbyten med returorder

Gör så här för att konfigurera systemet så att de stöder utbyten med returorder.

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Commerce-parametrar**. Ge alternativet **Behandla returorder som försäljningsorder** på snabbfliken **Kundorder** värdet **Ja**.
2. Kör jobbet **Globalt konfigurationsfördelningsschema** (**1110**).

## <a name="make-an-exchange"></a>Gör ett byte

När systemet är konfigurerat enligt beskrivningen i föregående avsnitt kommer kassaanvändaren fortfarande välja en försäljningsorder eller en försäljningsfaktura för att behandla en retur, precis som i tidigare versioner av appen. Men när de returnerade artiklarna läggs till i kundvagnen kommer användaren att kunna lägga till nya försäljningsrader i vagnen.

För dessa nya försäljningsrader måste användaren ange alla attribut som krävs för att behandla en kundorderrad. Bland dessa attribut ingår uppfyllelseplatsen och leveransmetoden. Betalningen för transaktionen är nettot av returorderraderna och försäljningsorderraderna. När transaktionen betalas bokförs returordern som ett försäljningsorderdokument i Headquarters, och systemet fakturerar omedelbart returraderna.

Tre nya beloppsfält har lagts till i kundvagnen för att ge bättre inblick i vagnens olika belopp. Du kan använda skärmdesignern för att göra dessa nya fält tillgängliga i kassaanvändargränssnittet.

- **Utnyttjad insättning** – Insättningsbeloppet som används i en transaktion när användaren hämtar upp en kundorder. Om det inte finns någon insättningsåsidosättning och en tioprocentig insättning har konfigurerats är beloppet i detta fält 90 procent av kundorderns totalbelopp.
- **Utför belopp** – Det totala beloppet för rader där leveransläget var **Utför** när kundordern skapades eller redigerades, eller under ett kundorderutbyte. Beloppet i detta fält omfattar moms och avgifter.
- **Returbelopp** – Det totala beloppet för rader med negativa kvantiteter under kundorderutbytet. Beloppet i detta fält omfattar moms och avgifter.


[!INCLUDE[footer-include](../includes/footer-banner.md)]