---
title: "Konfigurera och behandla ett utbyte för en returorder"
description: "I detta avsnitt beskriver vi hur du konfigurerar ett utbyte för en returorder i Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 3331b984693c58c6ee8c49b98ed7d3a8df5b79ff
ms.openlocfilehash: 45b628376a483d3d639e5c018dd93570ed8ce7af
ms.contentlocale: sv-se
ms.lasthandoff: 12/04/2018

---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Konfigurera och behandla ett utbyte för en returorder

[!include [banner](includes/banner.md)]

I tidigare versioner av Microsoft Dynamics 365 for Retail behandlades returer mot en kundorder genom att returorderdokumentet i Butik administration användes. Returorderdokumentet går dock att använda för att enbart behandla produkter som returneras. De returnerade produkterna anges med en negativ kvantitet på returorderraderna. Försäljningar anges med en positiv kvantitet. Returorderdokumentet stöder emellertid inte positiva kvantiteter. Tidigare versioner av Retail stödde på grund av denna begränsning inte scenarier där produktbyten gjordes med hjälp av returorderdokumentet.

Denna funktion har dock lagts till så att det ska gå att byta ut produkter på returorder. Retail använder nu försäljningsorderdokumentet i stället för returorderdokumentet för att bearbeta dessa typer av transaktioner.

## <a name="configure-retail-to-support-exchanges-on-return-orders"></a>Konfigurera Retail för att stödja utbyten med returorder

Gör så här för att konfigurera systemet så att de stöder utbyten med returorder.

1. Öppna **Retail \> Administrationsinställning \> Parametrar \> Butiksparametrar**. Ge alternativet **Behandla returorder som försäljningsorder** på snabbfliken **Kundorder** värdet **Ja**.
2. Kör jobbet **Globalt konfigurationsfördelningsschema** (**1110**).

## <a name="make-an-exchange"></a>Gör ett byte

När systemet är konfigurerat enligt beskrivningen i föregående avsnitt kommer kassaanvändaren fortfarande välja en försäljningsorder eller en försäljningsfaktura för att behandla en retur, precis som i tidigare versioner av Retail. Men när de returnerade artiklarna läggs till i kundvagnen kommer användaren att kunna lägga till nya försäljningsrader i vagnen.

För dessa nya försäljningsrader måste användaren ange alla attribut som krävs för att behandla en kundorderrad. Bland dessa attribut ingår uppfyllelseplatsen och leveransmetoden. Betalningen för transaktionen är nettot av returorderraderna och försäljningsorderraderna. När transaktionen betalas bokförs returordern som ett försäljningsorderdokument i Butik administration, och systemet fakturerar omedelbart returraderna.

Tre nya beloppsfält har lagts till i kundvagnen för att ge bättre inblick i vagnens olika belopp. Du kan använda skärmdesignern för att göra dessa nya fält tillgängliga i kassaanvändargränssnittet.

- **Utnyttjad insättning** – Insättningsbeloppet som används i en transaktion när användaren hämtar upp en kundorder. Om det inte finns någon insättningsåsidosättning och en tioprocentig insättning har konfigurerats är beloppet i detta fält 90 procent av kundorderns totalbelopp.
- **Utför belopp** – Det totala beloppet för rader där leveransläget var **Utför** när kundordern skapades eller redigerades, eller under ett kundorderutbyte. Beloppet i detta fält omfattar moms och avgifter.
- **Returbelopp** – Det totala beloppet för rader med negativa kvantiteter under kundorderutbytet. Beloppet i detta fält omfattar moms och avgifter.

