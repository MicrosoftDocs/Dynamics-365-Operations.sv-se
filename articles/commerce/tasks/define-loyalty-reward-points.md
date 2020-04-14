---
title: " Definiera förmånsbelöningspoäng"
description: Den här proceduren går igenom hur du definierar lojalitetsbelöningspoäng.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e40ebcbf3ab1befc641ae34571a8b974bd0425a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140886"
---
# <a name="define-loyalty-reward-points"></a> Definiera förmånsbelöningspoäng

[!include [banner](../includes/banner.md)]

Den här proceduren går igenom hur du definierar lojalitetsbelöningspoäng. Du bör ställa in lojalitetsbelöningspoäng innan du ställer in ett bonusprogram. I proceduren används demonstrationsföretaget USRT.

1. Gå till Butik och handel > kunder > lojalitet > Lojalitet extrapoäng.
2. Klicka på Ny.
3. Skriv ett värde i fältet Belöningspoäng-ID.
4. Ange ett värde i fältet Beskrivning.
5. Välj ett alternativ i fältet Belöningspoängtyp.
    * Välj Kvantitet om du vill belöningspoängen ska avrundas till närmaste heltal. Välj om du vill att extrapoäng ska avrundas enligt valuta avrundningsregler. Om du väljer Kvantitet, hoppa över nästa steg i den här proceduren.  
6. Ange ett värde i fältet Valuta.
    * För belöningspoäng av beloppstyp kommer alla utfärdade poäng ha den valda valutan. För belöningspoäng av kvantitetstyp Det här fältet inte tillämpa-överhoppet det här steget.  
7. Markera eller avmarkera kryssrutan Kan lösas in.
8. Ange ett nummer i fältet Rangordning av inlösen.
    * Rangordning av inlösen används när två eller fler inlösbara belöningspoäng kan användas för att betala för produkter. Om de två belöningspoängen har samma belopp att lösa in rankningen, visas den, som behöver nedre antal poäng, användas.  
9. Ange ett nummer i fältet Värde för utgångstid.
    * Belöningspoängen ska upphöra det angivna antalet dagar, månader eller år efter att poängen har utfärdas. Värdet 0 innebär att lojalitetsbelöningspoängen aldrig ska upphöra.  
10. Välj ett alternativ i fältet Enhet för utgångstid.
11. Klicka på Spara.

