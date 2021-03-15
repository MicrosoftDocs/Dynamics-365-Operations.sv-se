---
title: Kassaförbättringar för serialiserade produkter
description: Detta avsnitt listar förbättringar som har gjorts på serialiserade produkter i syfte att hjälpa dig att spara tid och bli mer produktiv.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-08-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b76d542f64979d28367cacb234669c9825b2d8aa
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982351"
---
# <a name="point-of-sale-pos-improvements-for-serialized-products"></a>Kassaförbättringar för serialiserade produkter

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Översikt

Baserat på inställningarna i administration för Commerce kan produkterna klassificeras som antingen serialiserade eller icke-serialiserade. När produkterna serialiseras kan respektive vara tilldelas ett unikt nummer som hjälper dig att spåra garantier och artiklar, samt bekräfta ägarskap. Även om möjligheten att tillhandahålla serienummer för serialiserade produkter redan fanns i vårt moderna kassasystem/kassasystem via moln har vissa förbättringar införts i syfte att hjälpa kassapersonalen att spara tid och vara mer produktiv.

## <a name="pos-improvements"></a>Kassaförbättringar

- **Serienummer krävs inte före POS** – Tidigare måste en kassör som lade till en serialiserad produkt i transaktionen även ange ett serienummer. Detta krav blev ett problem i samband med kundmöten då kassörer och säljmedarbetare hade möjlighet till merförsäljning. Före betalsteget uppdaterades produkterna ofta i kundvagnen. Varje gång en kassör lade till en ny produkt efterfrågade systemet därför serienumret. Dialogrutan för serienummer innehåller nu knappen **Lägg till senare**. Säljmedarbetarna kan därför lägga till varan i transaktionen, men kan ange serienumret senare. Säljmedarbetarna kan snabbt lägga till och byta ut serialiserade varor i kundvagnen och sedan kan ange serienumret precis före POS. Om serienumret inte anges för en serialiserad produkt kommer an kassör som försöker slutföra transaktionen att få ett felmeddelande. Detta meddelande anger att kassören måste ange de serienummer som saknas innan han eller hon kan fortsätta.

    En kommentar visas under transaktionsraden för varje enskild serialiserad vara där serienumret hoppades över. Denna kommentar anger att serienumret inte har angetts för varan. Kassören kan därför snabbt hitta varor som saknar ett serienummer.

    Den nya åtgärden **Lägg till serienummer** tillhandahåller även serienummer för varor som saknar serienummer. Ett angivet serienummer kan inte redigeras. Kassören måste ogiltigförklara raden och lägga till produkten på nytt.
    
- **Inga serienummer krävs för att lägga kundorder** – Kundorder kan läggas i en butik och utföras från en annan. En kassör som lägger en kundorder behöver inte ange något serienummer. Serienumret anges i samband med plock eller hämtning. Ett serienummer måste emellertid anges för samtliga radobjekt som leveranstypen **Utkörning** väljs för. I annat fall kan transaktionen inte slutföras.
- **Serialiserade produkter sammanställs inte på transaktionsskärmen** – Inställningen **Sammanställda produkter** i fältgruppen **Terminal** på sidan **Funktionalitetsprofil** låter dig sammanställa samma icke-serialiserade produkter på transaktionsskärmen. När samma produkter sammanställs blir de lättare att se i transaktionsrutnätet. Eftersom serienummer som regel är unika och säljare inte behöver ange serienummer före POS, gäller inställningen **Sammanställda produkter** emellertid inte serialiserade produkter. Därför kommer serialiserade produkter inte att sammanställas på transaktionsskärmen om inställningen **Sammanställ produkter** väljs.
- **Möjlighet att söka efter journalerna med serienummer** – Journalerna går nu dessutom att söka med serienummer. Öppna åtgärden Journaler och tryck på knappen Avancerad sökning i appfältet. Knappen Lägg till filter gör det möjligt att även använda ett filter vid sökning efter serienummer.


[!INCLUDE[footer-include](../includes/footer-banner.md)]