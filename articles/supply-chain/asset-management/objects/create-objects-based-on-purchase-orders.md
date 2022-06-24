---
title: Skapa tillgångar baserade på inköpsorder
description: I denna artikel beskrivs hur du kan skapa en lista över tillgångsartiklar som kan användas som underlag för att skapa tillgångar för underhållsjobb i Tillgångshantering.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectItem, EntAssetPendingAssets
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bee66e2d35af6daa8d86539e52b558bde3c79a1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893712"
---
# <a name="create-assets-based-on-purchase-orders"></a>Skapa tillgångar baserade på inköpsorder

[!include [banner](../../includes/banner.md)]

 

I denna artikel beskrivs hur du kan skapa en lista över tillgångsartiklar som kan användas som underlag för att skapa tillgångar för underhållsjobb i Tillgångshantering. Baserat på tillgångsartiklarna kan du visa en lista över inköpsorderrader som har skapats på dessa artiklar. Syftet med den här funktionen är att enkelt skapa en tillgång i Tillgångshantering baserat på en inköpsorder.

Först ställer du in de artiklar som ska användas för att skapa tillgångar från en inköpsorder i **tillgångsartiklar**. När du har skapat en inköpsorderrad skapar du tillgångarna i **väntande tillgångar**. Det är möjligt att bestämma i vilket skede av inköpsordern som tillgången ska skapas.


## <a name="select-asset-items"></a>Välj tillgångsartiklar

1. Klicka på **Tillgångshantering** > **inställningar** > **tillgångar** > **artiklar**.
2. Klicka på **Ny** om du vill skapa en ny tillgångsartikel.
3. Välj artikeln i fältet **Artikelnummer**. När du lämnar fältet infogas artikelnamnet automatiskt i fältet **produktnamn**.
4. På snabbfliken **Allmänt** väljer du en tillgångstyp för artikeln.
5. Välj tillgångstillverkare och modell för artikeln.
6. Spara artikeln.


## <a name="create-assets-from-pending-assets"></a>Skapa tillgångar från väntande tillgångar

1. Klicka på **Tillgångshantering** > **allmänt** > **tillgångar** > **väntande tillgångar**.
2. Du kommer att se en uppdaterad lista över inköpsorder baserat på de artiklar som valts i **tillgångsartiklar**.
3. Du kan filtrera status för inköpsorder för att välja vid vilket livscykeltillstånd som tillgången ska skapas. Du kanske till exempel bara vill skapa tillgångar när en produktinleverans har bokförts på en inköpsorder.
4. Välj länken **referensnummer** på en inköpsorderrad om du vill visa detaljerad information om artikeln.
5. Om du vill redigera vilka dimensioner som visas på snabbfliken **lagerdimensioner** klickar du på knappen **Visa dimensioner** och gör dina val.
6. Om du vill skapa en tillgång baserat på en inköpsorderrad markerar du kryssrutan i kolumnen **Markera** för den raden på listsidan och klickar på **skapa tillgångar**. Ett meddelande visas som informerar dig om tillgångs-ID.
7. Välj tillgången i listan **alla tillgångar** och klicka på knappen **redigera** för att lägga till mer information till tillgången.
8. I **väntande tillgångar**, om du vill ta bort en rad eftersom du inte vill skapa en tillgång, markerar du kryssrutan i kolumnen **Markera** för raden och klickar på **ignorera väntande tillgångar**. Ett meddelande visas som informerar dig om tillgångs-ID. Du tar inte bort inköpsordern eller försäljningsordern, bara den post som du kunde ha skapat en tillgång för i **tillgångshanteraren**.

>[!NOTE]
>Alla produktdimensioner (storlek, färg, konfiguration etc.) överförs automatiskt till tillgångsattribut. Spårningsdimensioner (serienummer) lagras direkt på tillgången när tillgången skapas.


## <a name="find-pending-assets"></a>Hitta väntande tillgångar

Du kan köra en **väntande tillgångsräkning** för att kontrollera väntande tillgångar. Den här funktionen kan till exempel användas för att ta emot ett meddelande varje gång en väntande tillgång är redo att skapas som en tillgång.

1. Klicka på **Tillgångshantering** > **periodisk** > **tillgångar** > **väntande tillgångsräkning**.
2. Klicka på **OK** för att köra jobbet och uppdatera listan i **väntande tillgångar**.
3. Du kan konfigurera det här jobbet så att det körs som ett batchjobb, till exempel en gång per dag.

**Varning:** om data ändras på en inköpsorder *efter* att du har skapat en tillgång baserat på artikeln, återspeglas inte dessa ändringar på tillgången.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]