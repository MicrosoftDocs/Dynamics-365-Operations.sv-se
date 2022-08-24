---
title: " Definiera förmånsbelöningspoäng"
description: Den här proceduren går igenom hur du definierar lojalitetsbelöningspoäng.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: RetailLoyaltyRewardPoints
ms.openlocfilehash: 9acd1429d17393f19a5e059b90a48b0b103535d3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268903"
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
