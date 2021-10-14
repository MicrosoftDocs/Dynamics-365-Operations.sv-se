---
title: Ändra koncerninterna order
description: I det här ämnet förklaras förändrade koncernintern orderfunktioner
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 1129794bf0ac6513770f8b2a0eeb7fb6154d7942
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548549"
---
# <a name="change-intercompany-orders"></a>Ändra koncerninterna order

[!include [banner](../../includes/banner.md)]

Om du ändrar en koncernintern försäljnings- eller inköpsorder visas ändringen även på motsvarande försäljnings- eller inköpsorder i företaget.

## <a name="adding-new-lines"></a>Lägga till nya rader

Du kan lägga till nya rader på en koncernintern försäljningsorder och inköpsorder om den ursprungliga försäljningsordern ingår i den koncerninterna orderkedjan. Du kan också lägga till nya rader om den ursprungliga försäljningsordern inte är en direktleverans. Om den ursprungliga försäljningsordern är en direkt leverans kan du bara lägga till nya orderrader till den interna företagets försäljningsorder och inköpsorder endast om fältet **Tillåt indirekt generering** väljs på snabbfliken **Koncerninterna inställningar** på den ursprungliga försäljningsordern.

## <a name="changing-prices-and-discounts"></a>Ändra priser och rabatter

Du kan ändra priser och rabatter om kryssrutorna **Tillåt prisredigering** och **Tillåt rabattredigering** har markerats på sidan **Koncernintern**.

Om du ändrar priset per enhet för någon av de befintliga raderna på den koncerninterna försäljningsorderraden ändras även enhetspriset på den koncerninterna försäljningsordern.

Om du ändrar något av rabattfälten på den koncerninterna försäljningsorderraden uppdateras alla berörda rabattfält på den koncerninterna försäljningsordern automatiskt.

## <a name="changing-and-adding-new-charges"></a>Ändra och lägga till nya avgifter

Du kan ändra avgifter om kryssrutorna **Tillåt prisredigering** och **Tillåt rabattredigering** har markerats på sidan **Koncernintern**.

Om du lägger till en ny kostnad i sidhuvudet i den koncerninterna försäljningsordern och en ny kostnad på den koncerninterna försäljningsraden kopieras båda tilläggen till den koncerninterna inköpsordern. Därför har den interna företagets försäljningsorder och den interna företagets inköpsorder samma totala belopp. Tilläggen kopieras aldrig till den ursprungliga försäljningsordern.

## <a name="copying-a-fee"></a>Kopiera en avgift

Om du vill kopiera en avgift till den ursprungliga försäljningsordern skapar du den som en ny försäljningsrad som har en artikel av typen **Tjänst**.

## <a name="changing-quantities-and-deleting-intercompany-purchases-and-sales-order-lines"></a>Ändra kvantiteter och ta bort rader från koncerninterna försäljnings- och inköpsorder

Du kan ändra kvantiteten eller ta bort en rad från en koncernintern försäljnings- eller inköpsorderrad endast om raden har skapats direkt från formuläret **försäljningsorder** eller **inköpsorder**. Den här ändringen innebär att den koncerninterna inköps- eller försäljningsordern eller orderraderna blir källan.

## <a name="origins-of-orders-and-order-lines"></a>Ursprung av order och orderrader

Koncerninterna order och orderrader kan ha ett av två ursprung:

- **Härledda** – Ordern skapades automatiskt från en koncernintern orderkedja.
- **Källa** – Ordern skapades manuellt av en användare.

Ursprunget visas i orderrubriken för koncerninterna inköps- och försäljningsorder i fältet **Ursprung**. Det här fältet finns på snabbfliken **Koncerninterna inställningar** på försäljningsordern och på snabbfliken **Inställningar** på inköpsordern.

Ursprunget **Härledda** och **Källa** gäller endast för koncerninterna order. Fältet **Ursprung** är tomt för alla andra typer av försäljnings- och inköpsorder och orderrader. Fältet är också tomt på den ursprungliga försäljningsordern.

## <a name="example-derived-origin"></a>Exempel: Härlett ursprung

Du skapar en ursprunglig försäljningsorder för en extern kund. Ordern innehåller en orderrad. Den här ursprungliga försäljningsordern leder till att en koncernintern inköpsorder med en rad skapas, vilket leder till att en koncernintern försäljningsorder med en rad skapas. Rubriken på den koncerninterna inköpsordern och orderraden skapas automatiskt utifrån den ursprungliga försäljningsordern.

Värdet i fältet **Ursprung** på snabbfliken **Inställningar** för den koncerninterna inköpsordern och snabbfliken **Koncerninterna inställningar** för de koncerninterna försäljningsorderhuvuden är **Härledda**. Värdet i fältet **Ursprung** på fliken **Raddetaljer** för inköpsorder- och försäljningsorderraderna är också **Härledd**.

Om en orderrad har ursprunget **Härledd** kan du inte ta bort orderraden direkt. Det går bara att ta bort orderraden från den källa som orderraden skapades från. Du kan också ändra den beställda kvantiteten från den källa som orderraden skapades från.

Om en ursprunglig försäljningsorder och en ursprunglig försäljningsorderrad ingår i den koncerninterna orderkedjan kan du ändra beställda kvantiteter och ta bort orderrader från den ursprungliga försäljningsordern.

## <a name="example-source-origin"></a>Exempel: Källsprung

Du skapar en inköpsorder för en koncernintern leverantör. Den koncerninterna inköpsordern och orderraden får ett ursprung av **Källa**. Detta innebär att den koncerninterna inköpsordern blir controller, och den koncerninterna försäljningsorder som skapas automatiskt i leverantörsföretaget får ursprunget **Härledd**.

De beställda kvantiteterna för en orderrad som har skapats på den koncerninterna inköpsordern kan inte heller ändras på den koncerninterna försäljningsordern. Orderraden kan bara tas bort från den koncerninterna inköpsordern. Om en ny rad läggs till den koncerninterna försäljningsordern har den koncerninterna försäljningsorderraden ursprunget **Källa**.

Om en ursprunglig försäljningsorder ingår i den koncerninterna orderkedjan går det alltid att styra alla koncerninterna order och orderrader från den ursprungliga försäljningsordern.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
