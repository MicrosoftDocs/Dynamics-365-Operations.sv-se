---
title: Visa versionshistorik för att återställa sidor och fragment
description: I den här artikeln beskrivs hur du visar versionshistoriken för en sida eller ett fragment och återgår till en tidigare version i Microsoft Dynamics 365 Commerce-webbplatsverktyget.
author: phinneyridge
ms.date: 06/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: c4d78103a3c08ee4052290fccf6750aba7eecf4a
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474110"
---
# <a name="view-version-history-to-revert-pages-and-fragments"></a>Visa versionshistorik för att återställa sidor och fragment

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs hur du visar versionshistoriken för en sida eller ett fragment och återgår till en tidigare version i Microsoft Dynamics 365 Commerce-webbplatsverktyget.

Med Commerce-webbplatsverktyget kan du visa versionshistoriken för en sida eller ett fragment, och vid behov återgå till en specifik tidigare version av ett dokument. När ett dokument är öppet kan du välja **Visa historik** i kommandofältet för att öppna en **Versionshistorik**-dialogruta där fliken **Version** listar historiken för alla versioner och spara aktiviteter för sidan eller fragmentet. Du kan sedan välja en tidigare version av dokumentet i listan, förhandsgranska det och återställa det som den aktuella versionen. Fliken **Aktivitet** i dialogrutan visar dokumentets fullständiga aktivitetshistorik, inklusive alla händelser som sparats, publiceras och tagits bort.

> [!NOTE]
> En ny version av ett dokument skapas varje gång en webbplatsredigerare utför ändringar och sedan väljer **Redigering slutförd** för dokumentet. 

Följ de här stegen om du vill visa versionshistoriken för en sida eller ett fragment och återgå till en tidigare version.

1. Öppna den sida eller det fragment som du vill visa versionshistoriken för i webbplatsverktyget.
1. Klicka på **Visa historik** i kommandofältet.

    ![Visa historikknappen.](./media/version-history-1.png)

1. I dialogrutan **Versionshistorik**, på fliken **Version**, väljer du en tidigare version av dokumentet. I egenskapsfönstret till höger visas en förhandsgranskning av den valda versionen samt information om vem som har ändrat den och när.

    ![Listvy för versionshistorik.](./media/version-history-2.png)

1. Välj **Förhandsgranska** om du vill se en fullt återgiven förhandsversion av vald dokumentversion. Om du vill stänga förhandsversionen och återvända till dialogrutan för **versionshistorik** väljer du **Stäng förhandsgranskning**.
1. Om du vill återställa en tidigare version av ett dokument markerar du det i listan på fliken **Version** och väljer **Återställ**. En meddelanderuta för **Återställ version \<version number\>** version visas, och du uppmanas att bekräfta återställningsåtgärden. 

    ![Knappen Återställ och rutan med bekräftelsemeddelande.](./media/version-history-3.png)

1. Om du vill fortsätta med återställningsåtgärden väljer du **Återställ**. Webbplatsverktyget uppdateras och visar den återställda versionen av sidan eller fragmentet.
1. Om du vill publicera den återställda versionen väljer du **Avsluta redigering** och sedan **Publicera**.
