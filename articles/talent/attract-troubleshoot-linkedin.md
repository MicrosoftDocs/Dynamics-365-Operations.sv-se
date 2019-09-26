---
title: Felsöka integrering med LinkedIn och Microsoft Dynamics 365 for Talent - Attract
description: I det här avsnittet beskrivs hur du felsöker problem när du försöker bokföra jobb till LinkedIn från Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 82ba7c505ba09e47f3c517c74c22e6aef7cd4e65
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739367"
---
# <a name="troubleshoot-integration-with-linkedin"></a>Felsöka integration med LinkedIn

[!include [banner](../includes/banner.md)]

Använd följande information för att felsöka problem som du kanske har när du försöker bokföra jobb till LinkedIn från Microsoft Dynamics 365 for Talent: Attract.

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a>Du kan inte logga in på LinkedIn från Attract

Om du har problem med att logga in på LinkedIn från Attract kan du försöka med följande:

1. Kontrollera att autentiseringsuppgifterna för LinkedIn som du angav i Attract är korrekta.
2. Om autentiseringsuppgifterna är korrekta kan du kontakta [LinkedIn-support](https://www.linkedin.com/help/linkedin).
3. Om problemet kvarstår kontaktar du [Microsoft support](./talent-support.md).

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a>Jobbpubliceringar från Attract visas inte på LinkedIn

Om jobbet inte visas på LinkedIn efter 24 timmar gör du så här:

1. Se till att ditt LinkedIn företags-ID mappas till din LinkedIn företagssida och att det anges korrekt i administrationscentret för Attract. Mer information om hur du ändrar LinkedIn-inställningar i administrationscentret finns i [ställa in integrering med LinkedIn](attract-admin-linkedin.md). För mer information om LinkedIn företags-ID:n, se [associera ditt LinkedIn företags-ID med LinkedIn jobbtavla - Vanliga frågor](https://www.linkedin.com/help/linkedin/answer/98972).
2. Kontrollera att adressen är fullständig genom att granska jobbinformationen på LinkedIn. För att kunna publicera ett jobb måste LinkedIn ha minst ort och land eller region för jobbet.
3. Kontrollera att jobbet inte duplicerar ett annat jobb som har publicerats på LinkedIn. LinkedIn publicerar inte jobb som är dubbletter av antingen LinkedIn Premium jobbplatser eller begränsade listor från en annan källa. Kontrollera att en annan person i företaget inte redan har publicerat jobbet manuellt.

## <a name="see-also"></a>Se även

[Vanliga frågor LinkedIn](./attract-linkedin-faq.md)

[Publicera jobb på LinkedIn från Attract](./attract-post-jobs-to-linkedin.md)

[Hitta kandidater med LinkedIn Recruiter](./attract-linkedin-recruiter.md)

[Skapa jobb](./creating-jobs-attract.md)

[Felsöka integration med LinkedIn](./attract-troubleshoot-linkedin.md)