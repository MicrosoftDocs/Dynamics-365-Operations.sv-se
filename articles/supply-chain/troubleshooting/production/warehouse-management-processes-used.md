---
title: Lagerstyrningsprocesser används just nu
description: När du reserverar eller frisläpper arbete kan du få ett meddelande om att lagerstyrningsprocesser för närvarande används. Lös problemet med ett av dessa steg.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bfda2fae824cdc64d722310d20cf16e6306d766c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477584"
---
# <a name="cant-reserve-or-release-work-because-processes-are-currently-being-used"></a>Det går inte att reservera eller frisläppa arbete eftersom processer används just nu

## <a name="symptoms"></a>Symtom

När du arbetar med diskret tillverkning får du följande felmeddelande:

> Lagerstyrningsprocesser används just nu. Om inte arbetsrader har registrerats ännu kan du annullera det skapade arbetet och eventuella last- eller leveransrader och sedan fortsätta med plocknings- eller leveransprocessen.

## <a name="cause"></a>Orsak

Det här problemet uppstår om du försöker reservera eller frisläppa arbete för en rad, men lager transaktionen har statusen *plockad*, vilket anger att materialet har plockats.

## <a name="resolution"></a>Lösning

Gör så här om du vill åtgärda problemet.

- Ändra tillbaka tillverkningsorderns status till *uppskattad* eller *frisläppt*.
- Öppna informationssidan för relevant produktionsorder. I åtgärdsfönstret på fliken **Lagerställe** i gruppen **Stopp** välj **Stoppa och häva plockning** för att häva plockning för alla plockade transaktioner. Välj sedan **ta bort stopp** för att bearbeta tillverkningsordern.

Här följer en förklaring av funktionerna *Häv plockning* och *Stopp*:
  
- **Häv plockning** – den här funktionen återför statusen för lagertransaktioner för strukturlisterader och receptrader som har status från *plockad* via *Har beställts*. När arbetet för plockning av råmaterial har slutförts ställs status på raderna in på *plockad*. Denna status förhindrar att tillverkningsordern återställs till statusen *Skapad*. I det här fallet kan du använda funktionen *Häv plockning* för att återställa transaktionerna från *plockad* status och sedan återställa tillverkningsordern till statusen *Skapad*.
- **Stopp** – den här funktionen ställer in en **stoppad** flagga på tillverkningsordern för att förhindra statusuppdatering för ordern. Du kan hitta **Stoppad** på snabbfliken **Distributionslager** på sidan med produktionsuppgifter.

> [!NOTE]
>
> - Knapparna visas bara när tillverkningsordern skapas för artiklar som är aktiverade för lagerprocesser.
> - Gruppen **Stopp** visa bara på **distributionslager** på åtgärdsfönstret på sidan med produktionsorder. Det visas inte på snabbfliken **Lagerställe** för listsidan **Produktionsorder**.
