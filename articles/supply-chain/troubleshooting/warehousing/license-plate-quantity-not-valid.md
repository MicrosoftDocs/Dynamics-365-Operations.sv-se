---
title: Kvantitet är inte giltigt när du registrerar inkommande order
description: Om kvantiteten som har allokerats för ett ID-nummer överskrider den kvantitet som fortfarande måste tas emot visas felmeddelandet "Kvantiteten är ogiltig".
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5099b320447bf59c72f5017564ea660f19c690a5
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477672"
---
# <a name="license-plate-quantity-is-not-valid-when-registering-inbound-orders"></a>Antal ID-nummer är inte giltigt när du registrerar inkommande order

## <a name="symptoms"></a>Symtom

När du registrerar inkommande order kan du få följande felmeddelande:

> Kvantiteten är ogiltig.

Om fältet **Grupperingspolicy för ID-nummer** anges till *Användardefinierad* för ett mobilt enhetsmenyalternativ som används för att registrera inkommande beställningar får du detta felmeddelande och du kan inte slutföra registreringen.

## <a name="cause"></a>Orsak

När *Användardefinierad* används som licens för grupperingspolicy, delar systemet upp det inkommande lagret i separat ID-nummer, enligt enhetssekvensgruppen. Om batch- eller serienummer används för att spåra artikeln som levereras måste kvantiteterna för varje batch eller serienummer anges per ID-nummer den som registreras. Om kvantiteten som har angetts för ett ID-nummer överskrider den kvantitet som fortfarande måste tas emot för de aktuella dimensionerna, visas felmeddelandet.

## <a name="resolution"></a>Lösning

När du registrerar ett objekt med hjälp av ett mobilt enhetsmenyalternativ där fältet **Grupperingspolicy för ID-nummer** anges till *Användardefinierad*, kan systemet kräva att du bekräftar eller anger ID-nummer, batch-nummer eller serienummer.

På sidan för ID-nummer bekräftelse visar systemet den kvantitet som har tilldelats för det aktuella ID-numret. På batch- eller seriebekräftelsesidorna visar systemet den kvantitet som fortfarande måste mottas på det aktuella ID-numret. Det kommer även att innehålla ett fält där du kan ange den kvantitet som ska registreras för kombinationen av ID- och batch- eller serienummer. Se då till att kvantiteten som registreras för ID-numret inte överstiger den kvantitet som fortfarande måste tas emot.

Alternativt, om för många ID-nummer genereras vid inkommande orderregistrering kan värdet på fältet **Grupperingspolicy för ID-nummer** ändras till *Gruppering av ID-nummer*, en ny enhetssekvensgrupp kan tilldelas objektet eller alternativet **Gruppering av ID-nummer** för enhetsseriegruppen kan inaktiveras.
