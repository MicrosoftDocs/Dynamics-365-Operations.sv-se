---
title: Felsöka integrering med LinkedIn och Microsoft Dynamics 365 Talent - Attract
description: I det här avsnittet beskrivs hur du felsöker problem när du försöker bokföra jobb till LinkedIn från Microsoft Dynamics 365 Talent - Attract.
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
ms.openlocfilehash: 42065f3d6b7ae9e7ad99b26c7692e41f8c36934d
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832987"
---
# <a name="troubleshoot-integration-with-linkedin-and-microsoft-dynamics-365-talent---attract"></a>Felsöka integrering med LinkedIn och Microsoft Dynamics 365 Talent - Attract

[!include [banner](includes/banner.md)]

Använd följande information för att felsöka problem som du kanske har när du försöker bokföra jobb till LinkedIn från Microsoft Dynamics 365 Talent: Attract.

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a>Du kan inte logga in på LinkedIn från Attract

Om du har problem med att logga in på LinkedIn från Attract kan du försöka med följande:

1. Kontrollera att autentiseringsuppgifterna för LinkedIn som du angav i Attract är korrekta.
2. Om autentiseringsuppgifterna är korrekta kan du kontakta [LinkedIn-support](https://www.linkedin.com/help/linkedin).
3. Om problemet kvarstår kontaktar du [Microsoft support](./talent-support.md).

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a>Jobbpubliceringar från Attract visas inte på LinkedIn

Om jobbet inte visas på LinkedIn efter 24 timmar gör du så här:

1. Se till att ditt LinkedIn företags-ID mappas till din LinkedIn företagssida och att det anges korrekt i administrationscentret för Attract. Mer information om hur du ändrar LinkedIn-inställningar i administrationscentret finns i [ställa in integrering med LinkedIn för Microsoft Dynamics 365 Talent - Attract](attract-admin-linkedin.md). För mer information om LinkedIn företags-ID:n, se [associera ditt LinkedIn företags-ID med LinkedIn jobbtavla - Vanliga frågor](https://www.linkedin.com/help/linkedin/answer/98972).
2. Kontrollera att adressen är fullständig genom att granska jobbinformationen på LinkedIn. För att kunna publicera ett jobb måste LinkedIn ha minst ort och land eller region för jobbet.
3. Kontrollera att jobbet inte duplicerar ett annat jobb som har publicerats på LinkedIn. LinkedIn publicerar inte jobb som är dubbletter av antingen LinkedIn Premium jobbplatser eller begränsade listor från en annan källa. Kontrollera att en annan person i företaget inte redan har publicerat jobbet manuellt.

## <a name="see-also"></a>Se även

[Vanliga frågor Attract-integration med LinkedIn](./attract-linkedin-faq.md)

[Publicera jobb på LinkedIn från Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md)

[Skaffa kandidater med LinkedIn Recruiter i Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md)

[Skapa, godkänna och bokföra jobb i Attract](./creating-jobs-attract.md)

[Felsöka integrering med LinkedIn och Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)
