---
title: Begränsa redigering av personlig information
description: Hindra medarbetare från att redigera kontaktinformation i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c82114f6600345ee5e2eb9c1c0629ae6c8f0b9a7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877697"
---
# <a name="restrict-editing-of-personal-information"></a>Begränsa redigering av personlig information


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

I den här artikeln beskrivs hur du begränsar medarbetare från att redigera kontaktinformation i Dynamics 365 Human Resources. Du kanske vill hindra medarbetarna från att redigera vissa kontaktuppgifter, till exempel deras företagsadress eller e-postadress.

> [!NOTE]
> Om du vill använda funktionen måste du först aktivera **(förhandsversion) begränsa anställda från att lägga till eller redigera adress- och kontaktinformation för utvalda syften** i Funktionshantering. Mer information om hur du aktiverar förhandsfunktioner finns i [Hantera funktioner](hr-admin-manage-features.md).<br><br>![Aktivera förhandsversion.](./media/hr-employee-self-service-restrict-enable.png)

## <a name="choose-the-information-an-employee-can-add-or-edit"></a>Välja vilken information en medarbetare kan lägga till eller redigera

1. I personal, välj **personalhantering**, välj **länkar** och välj sedan **personalparametrar**.

   ![Gå till personalparametrar.](./media/hr-employee-self-service-human-resources-parameters.png)

2. På sidan **Personalparametrar** väljer du fliken **Självbetjäning för medarbetare**.

   ![Välj Självbetjäning för medarbetare.](./media/hr-employee-self-service-tab.png)

3. På fliken **Självbetjäning för medarbetare**, avmarkera all information i avsnittet **Adress och kontaktinformation** som du inte vill att medarbetare ska lägga till eller redigera. I det här exemplet har vi avmarkerat **affärskontaktinformation**.

   ![Begränsa redigering av affärskontaktinformation.](./media/hr-employee-self-service-restrict-business.png)

4. Välj **Spara**.

   ![Spara ändringar.](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a>Medarbetarerfarenhet

När du har begränsat medarbetarna till att lägga till eller redigera kontaktdetaljer, kan de visa informationen, men det går inte att ändra den.

I det här exemplet, där anställda är begränsade från redigering **företags** kontaktinformation kan de fortfarande se informationen i **Självbetjäning för medarbetare**:

![Visa affärskontaktinformation.](./media/hr-employee-self-service-restrict-view.png)

När de väljer kontaktinformation för företaget visas dock fönstret **Redigera adress** visas som skrivskyddat och de kan inte kan inte ändra något av fälten.

![Affärskontaktinformation visas som skrivskyddade.](./media/hr-employee-self-service-restrict-read-only.png)

Om de dessutom väljer **Lägg till** för att lägga till ny adress kan de inte välja **Affär** från listrutan **Syfte**.

![Medarbetaren kan inte lägga till en företagsadress.](./media/hr-employee-self-service-restrict-add.png)

Medarbetare får samma erfarenhet när de väljer **Kontaktinformation** på sidan **Personlig information** och lägger till en ny adress. Listrutan **Syfte** visar bara de typer av information som de kan lägga till. 

![Medarbetaren kan inte välja Verksamhet i listrutan Syfte.](./media/hr-employee-self-service-restrict-purpose.png)

**Kontaktinformation** visar nu **Syfte** i rutnätet.

![Syftet visas i rutnätet Kontaktinformation.](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a>Se även

[Ställa in självbetjäning för medarbetare och chef – översikt](hr-employee-manager-self-service-overview.md)<br>
[Konfigurera Human Resources-parametrar](hr-setup-parameters.md)<br>
[Redigera personliga uppgifter](hr-employee-manager-self-service-edit-personal-information.md)
