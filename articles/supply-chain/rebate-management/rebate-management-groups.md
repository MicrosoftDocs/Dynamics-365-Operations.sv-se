---
title: Rabatthanteringsgrupper
description: I det här avsnittet beskrivs hur du ställer in Rabatthanteringsgrupper. Rabatthanteringsgrupper kan användas under rabattberäkningar och kan kopplas till en huvudpost.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e4e0fff3e60647795bda2f192a0421e9098315a5
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693400"
---
# <a name="rebate-management-groups"></a>Rabatthanteringsgrupper

[!include [banner](../includes/banner.md)]

Rabatthanteringsberäkningar kan baseras på grupper. Rabatthanteringsgrupper kan skapas för kunder, leverantörer och artiklar. De kan kopplas till en huvudpost.

## <a name="rebate-management-customer-groups"></a>Rabatthanteringsgrupper för kunder

Beräkningen för en grupp av kunder skapas ofta för en företagskedja, till exempel en kedja eller ett franchiseföretag. Den här typen av beräkning hör vanligtvis till en rabatt.

Ett avdrag beräknas ofta utan hänsyn till vem den godkända ordern såldes till. Det finns dock några undantag. En licenstagare kan exempelvis skapa ett avdragsschema där kundgrupp A får 4 procent, men kundgrupp B får bara tre procent.

### <a name="set-up-customer-groups"></a>Ställ in kundgrupper

Om du vill arbeta med kundgrupper för rabatthantering går du till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Kundgrupper**. Med knapparna i åtgärdsfönstret kan du lägga till och ta bort grupper efter behov. För varje grupp anger du följande fält:

- **Rabatthanteringsgrupp** – Ange ett unikt namn för gruppen.
- **Beskrivning** – Ange en beskrivning av gruppen om du vill ge mer information om hur den ska användas.

### <a name="manage-customer-group-assignments"></a>Hantera kundgruppstilldelningar

Varje kund kan tillhöra ett val annat antal rabatthanteringsgrupper. Om du vill visa och tilldela gruppmedlemmar kan du starta från grupplistan eller kundlistan.

Följ de här stegen om du vill visa, lägga till eller ta bort kunder för den valda gruppen.

1. Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Kundgrupper**.
1. Markera gruppen som du vill hantera.
1. I åtgärdsfönstret, välj **Kunder**. Sidan **Rabatthanteringsgrupper** visas och visar en lista med kunder som redan är medlemmar i den valda gruppen.
1. Välj om du vill lägga till en ny kund i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Kundkonto** – Välj kundkonto-ID.

1. Om du vill ta bort en kund från gruppen markerar du kunden och väljer **Ta bort** i åtgärdsfönstret.

Följ dessa steg för att visa, lägga till eller ta bort gruppuppdrag för en vald kund.

1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.
1. Välj den kund du vill arbeta med.
1. I åtgärdsfönstret på fliken **Kund** i gruppen **Rabatthantering** väljer du **Rabatthanteringsgrupper**. Sidan **Rabatthanteringsgrupper** visas och visar en lista med grupper som den valda kunden redan tillhör.
1. Välj om du vill lägga till en ny kund i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Rabatthanteringsgrupp** – Välj den grupp som kunden ska läggas till i.

1. Om du vill ta bort en kund från gruppen markerar du gruppen och väljer **Ta bort** i åtgärdsfönstret.

## <a name="rebate-management-vendor-groups"></a>Rabatthantering för leverantörsgrupper

Beräkningen för en grupp av leverantörer skapas ofta för en grupp med leveranspunkter. Den här typen av beräkning hör vanligtvis till en rabatt.

### <a name="set-up-vendor-groups"></a>Ställ in leverantörsgrupper

Om du vill arbeta med leverantörsgrupper för rabatthantering går du till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Leverantörsgrupper**. Med knapparna i åtgärdsfönstret kan du lägga till och ta bort grupper efter behov. För varje grupp anger du följande fält:

- **Rabatthanteringsgrupp** – Ange ett unikt namn för gruppen.
- **Beskrivning** – Ange en beskrivning av gruppen om du vill ge mer information om hur den ska användas.

### <a name="manage-vendor-group-assignments"></a>Hantera leverantörsgruppstilldelningar

Varje leverantör kan tillhöra ett val annat antal rabatthanteringsgrupper. Om du vill visa och tilldela gruppmedlemmar kan du starta från grupplistan eller leverantörlistan.

Följ de här stegen om du vill visa, lägga till eller ta bort leverantör för den valda gruppen.

1. Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Leverantörsgrupper**.
1. Markera gruppen som du vill hantera.
1. Klicka på **Leverantörer** i åtgärdsfönstret. Sidan **Rabatthanteringsgrupper** visas och visar en lista med leverantör som redan är medlemmar i den valda gruppen.
1. Välj om du vill lägga till en ny leverantör i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Leverantörskonto** – Välj leverantörskonto-ID.

1. Om du vill ta bort en leverantör från gruppen markerar du leverantören och väljer **Ta bort** i åtgärdsfönstret.

Följ dessa steg för att visa, lägga till eller ta bort gruppuppdrag för en vald leverantör.

1. Gå till **Leverantörsreskontra \> Leverantörer \> Alla leverantörer**.
1. Välj den leverantör du vill arbeta med.
1. I åtgärdsfönstret på fliken **Leverantör** i gruppen **Rabatthantering** väljer du **Rabatthanteringsgrupper**. Sidan **Rabatthanteringsgrupper** visas och visar en lista med grupper som den valda leverantör redan tillhör.
1. Välj om du vill lägga till en leverantör i en ny grupp, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Rabatthanteringsgrupp** – Välj den grupp som leverantören ska läggas till i.

1. Om du vill ta bort en leverantör från gruppen markerar du gruppen och väljer **Ta bort** i åtgärdsfönstret.

## <a name="item-rebate-groups"></a>Artikelrabattgrupper

Genom att gruppera artiklar blir du mer flexibel när rabatter och avdrag beräknas. Det här arbetssättet är ofta ett effektivare sätt att ställa in rabatter och avdrag för kunder och leverantörer.

### <a name="set-up-item-groups"></a>Ställ in artikelgrupper

Om du vill arbeta med artikelgrupper för rabatthantering går du till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Atikelgrupper**. Med knapparna i åtgärdsfönstret kan du lägga till och ta bort grupper efter behov. För varje grupp anger du följande fält:

- **Rabatthanteringsgrupp** – Ange ett unikt namn för gruppen.
- **Beskrivning** – Ange en beskrivning av gruppen om du vill ge mer information om hur den ska användas.

### <a name="manage-item-group-assignments"></a>Hantera artikelgruppstilldelningar

Varje artikel kan tillhöra ett val annat antal rabatthanteringsgrupper. Om du vill visa och tilldela gruppmedlemmar kan du starta från grupplistan eller artikellistan. Du kan också lägga till artiklar utifrån kategorihierarkin.

Följ de här stegen om du vill visa, lägga till eller ta bort artiklar för den valda gruppen.

1. Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Artikelgrupper**.
1. Markera gruppen som du vill hantera.
1. Klicka på **Artiklar** i åtgärdsfönstret. Sidan **Rabatthanteringsgrupper** visas och visar en lista med artiklar som redan är medlemmar i den valda gruppen.
1. Välj om du vill lägga till ny en artikel i gruppen, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Artikelkonto** – Välj artikelkonto-ID.

1. Om du vill ta bort en artikel från gruppen markerar du artikeln och väljer **Ta bort** i åtgärdsfönstret.

Följ dessa steg för att visa, lägga till eller ta bort gruppuppdrag för en vald artikel.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj den artikel du vill arbeta med.
1. I åtgärdsfönstret på fliken **Produkt** i gruppen **Rabatthantering** väljer du **Rabatthanteringsgrupper**. Sidan **Rabatthanteringsgrupper** visas och visar en lista med grupper som den valda artikel redan tillhör.
1. Välj om du vill lägga till artikeln i en ny grupp, välj **Ny** i åtgärdsfönstret för att lägga till en rad i rutnätet. Ange sedan följande fält för den nya raden:

    - **Rabatthanteringsgrupp** – Välj den grupp som artikeln ska läggas till i.

1. Om du vill ta bort en artikel från gruppen markerar du gruppen och väljer **Ta bort** i åtgärdsfönstret.

Följ de här stegen om du vill lägga till artiklar i en grupp baserat på kategorihierarkin.

1. Gå till **Rabatthantering \> Inställning av rabatthanteringsgrupper \> Artikelgrupper**.
1. Markera gruppen som du vill hantera.
1. Klicka på **Lägg till artiklar** i åtgärdsfönstret.
1. I dialogrutan **Lägg till artiklar** i fältet **Kategorihierarki**, välj en övre kategorihierarki.
1. Artikelhierarkin öppnas i det vänstra fönstret. Välj den hierarkinivå du vill ha. 
1. Artiklar från den valda hierarkin och hierarkinivån visas nu i högra fönstret. Följ dessa steg när du vill arbeta med fönstret:

    - Markera kryssrutan för varje artikel som du vill lägga till.
    - Markera kryssrutan i rutnätsrubriken om du vill markera alla artiklar som visas i listan.
    - Välj knappen **Visa markerad** för att filtrera rutnätet så att det bara visar de objekt du hittills har valt. Klicka på knappen igen om du vill återgå till den fullständiga listan.

1. Välj **OK** för att tillämpa artikelurvalet på den valda gruppen.
