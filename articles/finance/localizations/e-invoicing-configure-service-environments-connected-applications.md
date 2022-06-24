---
title: Konfigurera tjänstemiljöer och anslutna program
description: Detta ämne innehåller information om hur du konfigurerar dina tjänstemiljöer och anslutna program.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c1bb3f784148f04c01223ac4e280a18bacfe0e51
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853234"
---
# <a name="configure-service-environments-and-connected-applications"></a>Konfigurera tjänstemiljöer och anslutna program

[!include [banner](../includes/banner.md)]

Detta ämne innehåller information om hur du konfigurerar dina tjänstemiljöer och anslutna program. Processen är uppdelad i tre steg. Steg 1 är obligatoriskt och steg 2 och 3 är valfria.

## <a name="step-1-create-a-service-environment"></a>Steg 1: Skapa en tjänstemiljö

När du skapar din tjänstemiljö ska du definiera en lista över användare som kan distribuera globaliseringsfunktioner till den. I vissa scenarier kan du, om du vill, definiera en lista över externa program som kan kommunicera med e-faktureringstjänsten. Ställ in nummerserier om du vill använda dem i dina scenarier.

För att slutföra detta steg, se [Tjänstemiljöer](e-invoicing-service-environments.md).

## <a name="step-2-add-certificates-and-secrets"></a>Steg 2: Lägg till certifikat och hemligheter

Lägg till en referens till Microsoft Azure-nyckelvalv och -hemlighetet för att använda dem i dina scenarier. Detta steg är obligatoriskt om åtgärder i bearbetningsförlopp använder certifikat och hemligheter för digital signering eller kommunikation med externa webbtjänster.

Mer information om detta steg finns i [Kundcertifikat och hemligheter](e-invoicing-customer-certificates-secrets.md).

## <a name="step-3-configure-connected-applications"></a>Steg 3: Konfigurera anslutna program

För att ställa in kommunikationen mellan Dynamics 365 Finance- och Dynamics 365 Supply Chain Management-program och e-fakturering måste du konfigurera Ekonomi eller Supply Chain Management för att skapa ett anrop till e-faktureringstjänsten och förbereda affärsdata i en enhetlig struktur som kan transformeras till det nödvändiga elektroniska formatet. Ansökningar måste också bearbeta svaren från tjänsten på ett korrekt sätt. Du kan slutföra konfigurationen direkt i din Ekonomi- eller Supply Chain Management-miljö, eller också kan du slutföra den i Regulatory Configuration Service (RCS). Om du slutför konfigurationen i RCS kan du sedan distribuera den till din Ekonomi- eller Supply Chain Management-miljö. I det här steget ska du registrera det anslutna programmet för parameterdistribution.

För att slutföra detta steg, se [Anslutna program](e-invoicing-connected-applications.md).
