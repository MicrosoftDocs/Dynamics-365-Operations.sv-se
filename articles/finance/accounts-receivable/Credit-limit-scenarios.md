---
title: Scenarier för kreditgräns
description: I den här artikeln beskrivs hur kundens kreditgräns kontrolleras när kunden hör till en kundkreditgränsgrupp.
author: JodiChristiansen
ms.date: 06/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-06-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 60b17a6b7f57b468610974ae9bd05b7db3584cc1
ms.sourcegitcommit: 85141b21ac90f3db1b378c21f9c7f3d8f74e182f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2022
ms.locfileid: "9130266"
---
# <a name="credit-limit-scenarios"></a>Scenarier för kreditgräns

I Kredithantering kan en kreditgräns tilldelas kunder på kundnivå. Varje kund kan tilldelas en *kundkreditgränsgrupp*, och varje grupp har en kreditgräns. En kreditgräns kan därför även tilldelas kunder på gruppnivå. Alla kunder som tilldelas samma kundkreditgrupp har samma kreditgräns.

I allmänhet kontrolleras gruppkreditgränser före enskilda kreditgränser. Den enskilda kreditgränsen åsidosätter inte alltid gruppkreditgränsen.

I den här artikeln beskrivs fem scenarier som är relaterade till kundkreditgrupper och individuella kreditgränser.

## <a name="the-customer-group-credit-limit-is-more-than-the-individual-credit-limit"></a>Kreditgränsen för kundgrupp är högre än den individuella kreditgränsen

Kunden har till exempel en individuell kreditgräns på $10 000. Kunden tilldelas en kundkreditgrupp och gruppens kreditgräns är $15 000. I det här fallet är kundens "effektiva kreditgräns" $10 000 eftersom detta belopp är mindre än gruppgränsen. Spärregler kontrollerar först gruppgränsen. De kontrollerar sedan den enskilda gränsen. Eventuella försäljningsorder $10 000 kommer att blockeras.

## <a name="the-individual-credit-limit-is-more-than-the-customer-group-credit-limit"></a>Den individuella kreditgränsen är högre än kreditgränsen för kundgrupp

Kunden har till exempel en individuell kreditgräns på $20 000. Kunden tilldelas en kundkreditgrupp och gruppens kreditgräns är $15 000. I det här fallet är kundens effektiva kreditgräns $15 000, detta eftersom spärreglerna alltid kontrollerar gruppgränsen först. Eventuella försäljningsorder över $15 000 kommer att blockeras.

## <a name="the-individual-credit-limit-is-set-to-000-and-mandatory-credit-limit-is-set-to-yes"></a>Den individuella kreditgränsen är inställd på 0,00, och obligatorisk kreditgräns anges som Ja

Om kunden har en individuell kreditgräns som är satt till **0,00** och alternativet för **Obligatorisk kreditgräns** är inställt på **Ja** blir kundens effektiva kreditgräns $0,00, även om kunden tilldelas en kundkreditgrupp. På det här sättet kan kunden ingå i en grupp, men alla order går till Kredithantering.

## <a name="the-individual-credit-limit-is-set-to-000-and-unlimited-credit-limit-is-set-to-yes"></a>Den individuella kreditgränsen är inställd på 0,00, och kreditgränsen Obegränsad anges som Ja

Om kunden har en individuell kreditgräns som är satt till **0,00** men alternativet för **Obligatorisk kreditgräns** är inställt på **Ja** får kunden obegränsad kredit, även om han/hon tilldelas en kundkreditgrupp.

## <a name="the-individual-credit-limit-is-set-to-000-and-the-customer-is-part-of-a-customer-credit-group"></a>Den enskilda kreditgränsen är inställd på 0,00 och kunden ingår i en kundkreditgrupp

Kunden har till exempel en individuell kreditgräns som är inställd på **0,00**, alternativet **Obegränsad kredit** är inställt på **Nej** och alternativet **Obligatorisk kreditgräns** är inställt **Nej**. Kunden tilldelas en kundkreditgrupp och gruppens kreditgräns är $15 000. I det här fallet är kundens effektiva kreditgräns gruppens gräns, alltså $15 000. Därför spärras eventuella försäljningsorder för det beloppet. Detta gör att kreditgränsen kan hanteras på kundkreditgruppsnivå istället för på individuell kundnivå. Alla kunder som tilldelas samma grupp har samma kreditgräns.
