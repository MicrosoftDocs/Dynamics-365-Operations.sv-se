---
title: Regulatory Configuration Service (RCS) – ta bort en RCS-miljö
description: I den här artikeln beskrivs hur Regulatory Configuration Service (RCS) systemadministratör kan ta bort en RCS-miljö och relaterad data.
author: kfend
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, System Admin
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.custom: 97423
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
ms.openlocfilehash: bdcb6820ead72fce0f89bf80cc5e474cb3942724
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277253"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a>Regulatory Configuration Service (RCS) – ta bort en RCS-miljö

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur Regulatory Configuration Service (RCS) systemadministratör kan ta bort en RCS-miljö och relaterad data.

Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:

- Du måste ha tilldelats rollen **Systemadministratör** för RCS-miljön.
- Rollen **Systemadministratör** måste ha rollen **RCSDeleteEnvironmentDuty** tilldelad den.

## <a name="delete-an-rcs-environment"></a>Ta bort en RCS-miljö

1. Öppna RCS och välj arbetsytapanel **Elektronisk rapportering**.
2. I avsnittet **Relaterade länkar**, välj **Ta bort RCS-miljö**.

    ![Ta bort RCS-miljölänk i avsnittet Relaterade länkar.](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. Granska meddelandena om omfattningen av borttagningen av miljön i dialogrutan som visas.

    ![Meddelanden i dialogrutan Ta bort RCS-miljö.](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > Radering av en RCS-miljö kan inte återföras.
    >
    > Operationen tar bort den valda RCS-miljön och alla relaterade data, inklusive funktioner och konfigurationer som är lagrade i den globala databasen. Funktioner och konfigurationer som delas med andra organisationer tas bort och tas bort om de inte har några beroenden. Funktioner och konfigurationer som har beroenden markeras som utgått.

4. I fältet som finns anger du den globala unika identifieraren (GUID) för RCS-miljön för att bekräfta att du vill ta bort den. Miljöns GUID inkluderas i borttagningsmeddelandet.
5. Välj **Ta bort miljö**.
    
Din RCS-miljö och alla relaterade data raderas nu.

> [!IMPORTANT]
> När du har raderat en RCS-miljö går det inte att återställa data. En ny RCS-miljö kan skapas i alla tillgängliga RCS-regioner.
