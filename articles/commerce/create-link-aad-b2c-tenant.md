---
title: Skapa eller länka till en befintlig Azure AD B2C-klientorganisation i Azure-portalen
description: I den här artikeln beskrivs hur du skapar eller länkar en bvefintlig Azure Active Directory (Azure AD) B2C-innehavare i Microsoft Azure-portal.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 0aa12387f00ffc3dd10688c6385c7952f089ab12
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785295"
---
# <a name="create-or-link-to-an-existing-azure-ad-b2c-tenant-in-the-azure-portal"></a>Skapa eller länka till en befintlig Azure AD B2C-klientorganisation i Azure-portalen

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs hur du skapar eller länkar en Azure Active Directory (Azure AD) B2C-innehavare i Microsoft Azure-portal. Mer information finns i [Självstudie: Skapa en Azure Active Directory B2C klientorganisation](/azure/active-directory-b2c/tutorial-create-tenant).

Följ de här stegen om du vill skapa eller länka till en befintlig Azure AD B2C-innehavare i Azure-portalen.

1. Logga in på [Azure-portal](https://portal.azure.com/).
1. Från Azure-portal menyn, välj **skapa en resurs**. Se till att använda den prenumeration och katalog som kommer att vara ansluten till din Commerce-miljö.

    ![Skapa en resurs i Azure-portalen.](./media/B2CImage_1.png)

1. Gå till **identitet \>Azure Active Directory B2C**.
1. På sidan **Skapa ny B2C-klient eller länk till befintlig klient** använder du ett av alternativen nedan som bäst passar ditt företags behov:

    - **Skapa en ny Azure AD B2C innehavare**: Använd det här alternativet om du vill skapa en ny Azure AD B2C innehavare.
        1. Välj **Skapa ett nytt Azure AD B2C-innehavare**.
        1. Ange **organisationsnamnet** under organisationsnamn.
        1. Under **Initialt domännamn**, ange initialt domännamn.
        1. För **land eller region** välj land eller region.
        1. Välj **skapa** om du vill skapa innehavaren.

     ![Skapa en ny Azure AD-klientorganisation.](./media/B2CImage_2.png)

     - **Länka en befintlig Azure AD B2C-innehavare till min Azure-prenumeration**: Använd det här alternativet om du redan har en Azure AD B2C innehavare som du vill länka till.
        1. Välj **länka en befintlig Azure AD B2C-klient till mitt Azure-abonnemang**.
        1. Välj **Azure AD B2C innehavare** välj för B2C-innehavaren. Om meddelandet "inga bidragsberättigande B2C-innehavare hittades" visas i urvalsrutan har du inte en giltig B2C klientorganisation och behöver skapa en ny.
        1. För **Resursgrupp**, välj **Skapa nya**. Ange ett **namn** på den resursgrupp som ska innehålla innehavaren, välj **Välj resursgruppens plats** och välj **sedan skapa**.

    ![Länka en befintlig Azure AD B2C-klientorganisation till ett Azure-abonnemang.](./media/B2CImage_3.png)

1. När den nya Azure AD B2C skapas (detta kan ta en stund) visas en länk till den nya katalogen på instrumentpanelen. Länken leder till sidan "Välkommen till Azure Active Directory B2C".

    ![Länk till ny Azure AD-katalog](./media/B2CImage_4.png)

> [!NOTE]
> Om du har flera prenumerationer inom ditt Azure-konto eller har ställt in B2C-klienten utan att länka till en aktiv **prenumeration**, kommer en felsökningsannons att leda till att du kopplar klienten till en prenumeration. Markera felsökningsmeddelandet och följ instruktionerna för att lösa prenumerationsproblemet.

Följande bild visar ett exempel på en Azure AD B2C **felsökning** banderoll.

![Varnings som anger att katalogen inte har någon aktiv prenumeration.](./media/B2CImage_5.png)

## <a name="next-steps"></a>Nästa steg

För att fortsätta processen att ställa in B2C-innehavare Commerce, gå till [Skapa B2C-app](create-b2c-app.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Ställa in en B2C-innehavare i Commerce](set-up-b2c-tenant.md)

[Skapa B2C-applikationen](create-b2c-app.md)

[Skapa policyer för användarflöden](create-user-flow-policies.md)

[Lägg till sociala identitetsleverantör (valfritt)](add-social-identity-providers.md)

[Uppdatera Commerce headquarters med den nya Azure AD B2C-informationen](update-hq-aad-b2c-info.md)

[Konfigurera din B2C-innehavare i Commerce webbplatsskaparen](config-b2c-tenant-site-builder.md)

[Ytterligare B2C-information](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
