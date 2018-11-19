---
title: Intelligenta rekommendationer
description: "Det här avsnittet beskriver hur du kan använda maskininlärning för att ge rekommendationer för jobb och jobbsökande."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: fea36661c65739ef09261c82ec44e16c29fad0e7
ms.contentlocale: sv-se
ms.lasthandoff: 10/22/2018

---

# <a name="intelligent-recommendations"></a>Intelligenta rekommendationer

[!include[banner](../includes/banner.md)]

Maskininlärning kan hjälpa rekryterare och personalchefer att snabbt identifiera de bästa kandidaterna för en befattning. Den kan också hjälpa potentiella kandidater att hitta en befattning som passar deras profil och intressen. När dessa funktioner används och feedback ges förbättras rekommendationer.

> [!NOTE] 
> - Funktionerna för intelligent rekommendation finns endast med tillägget för omfattande anställning.
> - Om du vill aktivera funktionen för kandidat- och jobbrekommendationer måste en administratör aktivera alternativen för förhandsgranskning. I administrationscenter på fliken **Funktionshantering** ser du till att alternativet **Förhandsgranska funktioner** är inställt på **På**. Kontrollera sedan att de enskilda alternativen för **kandidatrekommendation** och **jobbrekommendation** ställs in på **på**.

## <a name="candidate-recommendations"></a>Kandidatrekommendationer

Eftersom jobbpubliceringar kan locka hundratals sökande, kan det vara svårt för rekryterare och personalchefer att hitta kandidater vars kvalifikationer och bakgrund bäst matchar befattningen. Genom att analysera sambandet mellan jobbeskrivning och krav och data från kandidatens meritförteckningar och profiler kan maskininlärning användas för att framställa kandidatrekommendationer. Kandidatrekommendationer kan hjälpa rekryterare och personalchefer identifiera de bästa talangerna och flytta dem till intervjufasen snabbare. För alla jobb, om det finns fler än tio kandidater eller potentiella kandidater som har meritförteckningar eller fullständiga profiler kommer de kandidater som bäst uppfyller jobbkraven att visas i avsnittet **Sökande att beakta** på sidan **Jobb**.

För alla rekommenderade kandidater kan du välja **visa kandidat** på kandidatkortet för att granska kandidatens profil och vidta åtgärder för hans eller hennes ansökan. Du kan använda den ellipsformade knappen (**...**) för att öppna kandidatens profil på en ny flik. Du kan också använda den ellipsformade knappen för att ge återkoppling om rekommendationen. På så sätt kan du finjustera rekommendationsmotorn och förbättra framtida rekommendationer. Eventuella rekommendationer som du inte gillar tas bort från avsnittet **sökande att beakta** när du uppdaterar sidan **Jobb**. Du kan använda feedbackkortet för att ange varför du inte tycker att rekommendationen är användbar.

## <a name="job-recommendations"></a>Jobbrekommendationer 

När en potentiell medarbetare använder jobbwebbplatsen för att ansöka om ett jobb, rekommenderas andra lediga befattningar inom organisationen. Dessa rekommendationer baseras på potentiella kandidatens tidigare ansökningar och på hans eller hennes meritförteckning eller kandidatprofil. Därför hjälper jobbrekommendationer potentiella kandidater att snabbt identifiera vilka jobb som passar dem bäst. Jobbrekommendationer ges till potentiella kandidater om mer än tio jobb publiceras på jobbwebbplatsen. Potentiella kandidater kan öppna detaljerna på en jobbpublicering från rekommendationskortet. De kan också ge feedback om en rekommendationen för att förbättra framtida rekommendationer.

