---
title: Konfigurera och behandla ett utbyte för en returorder
description: I den här artikeln beskriver vi hur du konfigurerar ett utbyte för en returorder i Dynamics 365 Commerce.
author: josaw1
ms.date: 07/28/2021
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
ms.openlocfilehash: f33c674e4110b4e45ac58e499a65da2509b00046
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845804"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Konfigurera och behandla ett utbyte för en returorder

[!include [banner](includes/banner.md)]

I tidigare versioner av Dynamics 365 Commerce behandlades returer mot en kundorder genom att returorderdokumentet i Headquarters användes. Returorderdokumentet går dock att använda för att enbart behandla produkter som returneras. De returnerade produkterna anges med en negativ kvantitet på returorderraderna. Försäljningar anges med en positiv kvantitet. Returorderdokumentet stöder emellertid inte positiva kvantiteter. Tidigare versioner av appen stödde på grund av denna begränsning inte scenarier där produktbyten gjordes med hjälp av returorderdokumentet.

Denna funktion har dock lagts till så att det ska gå att byta ut produkter på returorder. Commerce använder nu försäljningsorderdokumentet i stället för returorderdokumentet för att bearbeta dessa typer av transaktioner.

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>Konfigurera Commerce för att stödja utbyten med returorder

> [!NOTE]
> I Commerce 10.0.20 och senare finns en ny funktion med namnet "Enhetlig returbearbetningserfarenhet i kassan". Om du aktiverar funktionen behövs inte konfigurationsstegen nedan. **Behandla returorder som försäljningsorder** blir en permanent konfigurerad inställning och du kan inte ändra den.

Följ de här stegen för att konfigurera systemet att stödja utbyten med returorder (om du inte har aktiverat funktionen **Enhetlig returbearbetningserfarenhet i kassan**).

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
