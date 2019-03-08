---
title: Ställ in produkter som antingen kan produceras eller anskaffas
description: Produkter kan införskaffas på flera olika sätt - de kan produceras (tillverkas) eller anskaffas (köpas). Den här artikeln beskriver några typiska punkter att beakta när du konfigurerar produkter för att stödja fleranskaffning.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a910b5782c8f15cfdd4cf93ea883bc28a5ce8e1a
ms.sourcegitcommit: 2ebea3cbddfa0a5ef0e0fd13d3693da6152bc288
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2019
ms.locfileid: "338462"
---
# <a name="set-up-products-that-can-be-produced-or-procured"></a>Ställ in produkter som antingen kan produceras eller anskaffas

[!include [banner](../includes/banner.md)]

Produkter kan införskaffas på flera olika sätt - de kan produceras (tillverkas) eller anskaffas (köpas). Den här artikeln beskriver några typiska punkter att beakta när du konfigurerar produkter för att stödja fleranskaffning. 

Fleranskaffning används vanligtvis för en inköpt artikel som i vissa fall tillverkas, eller när en artikel som primärt var en tillverkad artikel ändras så att den nu är primärt en inköpt artikel. Artikeln betecknas inledningsvis som en tillverkad artikel så att strukturlistan och flödesinformationen kan definieras, och så att tillverkningsorder kan användas för artikeln. Produktiontypen ska anges som **Strukturlista** (eller vid processtillverkning som **Recept** eller **Samprodukt**).

När du använder standardkostnad kan artikelkostnadsposten beräknas för den tillverkade artikeln. Men artikelkostnadsposten kanske inte matchar standardenkostnaden som du vill ha i inköpssyfte. I detta fall måste standardkostnaden anges och aktiveras manuellt för artikelkostnadsposten. Överväg att använda en särskild strukturlista och ett flöde som representerar den produktens leveransmix över en räkenskapsperiod, för att minimera avvikelser över tid. Dessutom kan en tillverkad artikel på en plats överförs till en annan plats. Därför måste artikelns kostnad registreras och aktiveras manuellt för den plats som artikeln ska överföras till. När du använder den tillverkade artikeln som en komponent i produkter på högre nivåer, ska komponentens kostnad behandlas som en inköpt artikel. Denna riktlinje gäller oavsett om komponentens kostnader beräknas eller registreras manuellt. Med andra ord ska strukturlisteberäkningen behandla artikelns kostnader som en inköpt komponent, i stället för att använda artikelns strukturliste- och flödesinformation för att beräkna kostnader. 

Du kan förhindra den här beräkningen genom att välja flaggan **Stoppa nedbrytningen** som bäddas in i strukturlisteberäkningsgruppen som tilldelas artikeln. För att förhindra att huvudplaneringsberäkningar bryter ned behov via artikeln, ställs nedbrytningsgränsen in på = (noll) dagar i artikeldisponering eller i disponeringsgruppen. Huvudplaneringsberäkningen kommer sedan att behandla artikeln som en inköpt artikel och kan inte utföra fler beräkningar för artikelns strukturliste- och flödesinformation.





