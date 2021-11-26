---
title: Koncerninterna parametrar
description: Det här ämnet förklarar koncerninterna parametrar
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: face3cbd21998edcba528548ec4ae52354330aa3
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778507"
---
# <a name="intercompany-parameters"></a>Koncerninterna parametrar

[!include [banner](../../includes/banner.md)]

I en koncernintern organisation kan du ställa in parametrar som bestämmer hur du handlar mellan olika juridiska personer. Parametrarna avgörs av de fält du väljer. Du kan välja olika kombinationer som återspeglar olika handelsscenarion.

Följande två exempel beskriver scenarier för koncerninterna organisationer, en med två nivåer och en med tre nivåer.

## <a name="example-1-two-level-intercompany-chain"></a>Exempel 1: Två koncernintern kedja i 2 nivåer

Den koncerninterna organisationen innehåller följande juridiska personer:

- Juridisk person A – Säljer till externa kunder, men saknar lager. Den här juridiska personen köper från Juridisk enhet B.
- Juridisk enhet B – Säljer endast till Juridisk person A.

Båda juridiska personerna kan sälja till och köpa från varandra.

I detta exempel baseras priserna på den ursprungliga försäljningsordern, som skickas till externa kunder, alltid på försäljningspriset. Priserna på den koncerninterna försäljningsordern och den koncerninterna inköpsordern kontrolleras av det interna försäljningspriset/överföringspriset på den koncerninterna försäljningsordern i juridisk person B.

Filhuvudinformationen kontrolleras hela vägen från den ursprungliga försäljningsordern till den externa kunden. Eventuella ändringar i den koncerninterna försäljningsordern synkroniseras inte till den ursprungliga försäljningsordern.

I juridisk person A, på sidan **Koncernintern** för leverantörer, välj **Inköpsorderpolicyer**. Välj följande fält i fältgruppen **Ursprunglig försäljningsorder (direktleverans)**:

- **Skriv ut följesedel automatiskt**
- **Bokför faktura automatiskt**
- **Skriv ut faktura automatiskt**

I fältgruppen **Koncernintern inköpsorder (direktleverans)**, välj följande fält:

- **Bokför faktura automatiskt**

I gruppen **Ursprunglig försäljningsorder <-> Koncernintern inköpsorder** välj följande fält:

- **Kundinformation**
- **RMA-nummer**

I fältgruppen **Koncernintern inköpsorder <-> Ursprunglig försäljningsorder** välj följande fält:

- **Kundinformation**
- **RMA-nummer**
- **Batchnummer**
- **Serienummer**

I juridisk person B, på sidan **Koncernintern** för kunder, välj **Försäljningsorderpolicyer**. Välj följande fält i fältgruppen **Skapa koncernintern försäljningsorder**:

- **Försäljningsordernumrering** : **Företag + ursprungligt nummer**
- **Tillåt samlingsuppdatering av dokument för den ursprungliga kunden**

I fältgruppen **Koncerninterna försäljningsorderpriser** välj följande fält:

- **Pris- och rabattsökning**
- **Tillåt redigering av pris**
- **Tillåt redigering av rabatt**

I fältgruppen **Koncernintern försäljningsorder \> Koncernintern inköpsorder** välj följande fält:

- **Batchnummer**
- **Serienummer**

## <a name="example-2-three-level-intercompany-chain"></a>Exempel 2: koncernintern kedja i 3 nivåer

Den koncerninterna organisationen innehåller följande juridiska personer:

- Juridisk enhet A – En juridisk person som säljer till externa kunder och köper från Juridisk enhet B.
- Juridisk enhet B – En juridisk person för produktion eller distribution som inte kan leverera produkter och köper från Juridisk enhet C.
- Juridisk enhet C – En juridisk person för produktion eller distribution som levererar produkter till Juridisk enhet B.

Interna överföringspriser mellan juridiska personer B och C är till självkostnadspris från den säljande juridiska personen i början av kedjan. Den står också till företagets kostnad för den juridiska personen A, som säljer till externa kunder. Men priser på den ursprungliga försäljningsordern till externa kunden är alltid baserad på försäljningspriset.

Priser på alla koncerninterna försäljningsorder och koncerninterna inköpsorder kontrolleras på den koncerninterna försäljningsordern. Den styrs i början av kedjan. Därför kontrollerar juridisk enhet C, som säljer till Juridisk person B, priset. Koncernens prissättning av försäljningsorder baseras på den interna försäljningen eller överföringsprissättningen som ställs in i juridisk enhet C.

Filhuvudinformationen kontrolleras hela vägen från den ursprungliga försäljningsordern till den externa kunden. Eventuella ändringar i de koncerninterna orderna synkroniseras inte till den ursprungliga försäljningsordern.

Följande parametrar måste väljas:

I juridisk person A, på sidan **Koncernintern** för leverantörer, välj **Inköpsorderpolicyer**. Välj följande fält i fältgruppen **Ursprunglig försäljningsorder (direktleverans)**:

- **Skriv ut följesedel automatiskt**
- **Bokför faktura automatiskt**
- **Skriv ut faktura automatiskt**

I fältgruppen **Koncernintern inköpsorder (direktleverans)**, välj följande fält:

- **Bokför faktura automatiskt**

I fältgruppen **Ursprunglig försäljningsorder <-> Koncernintern inköpsorder** välj följande fält:

- **Kundinformation**
- **RMA-nummer**

I fältgruppen **Koncernintern inköpsorder <-> Ursprunglig försäljningsorder** välj följande fält:

- **Kundinformation**
- **RMA-nummer**
- **Batchnummer**
- **Serienummer**

I juridisk person B, på sidan **Koncernintern** för kunder, välj **Försäljningsorderpolicyer**. Välj följande fält i fältgruppen **Skapa koncernintern försäljningsorder**:

- **Försäljningsordernumrering** : **Företag + ursprungligt nummer**
- **Tillåt samlingsuppdatering av dokument för den ursprungliga kunden**

I fältgruppen **Koncernintern försäljningsorder \> Koncernintern inköpsorder** välj följande fält:

- **Batchnummer**
- **Serienummer**

I fältgruppen **Koncernintern bokföring av kundfaktura** välj följande fält:

- **Pris per enhet är lika med självkostnad**
- **Initiera bokföring av ursprunglig kundfaktura**

I juridisk person B, på sidan **Koncernintern** för leverantörer, välj **Inköpsorderpolicyer**. Välj följande fält i fältgruppen **Ursprunglig försäljningsorder (direktleverans)**:

- **Skriv ut följesedel automatiskt**
- **Bokför faktura automatiskt**
- **Skriv ut faktura automatiskt**

I fältgruppen **Koncernintern inköpsorder (direktleverans)**, välj följande fält:

- **Bokför faktura automatiskt**

I fältgruppen **Ursprunglig försäljningsorder <-> Koncernintern inköpsorder** välj följande fält:

- **Kundinformation**
- **RMA-nummer**
- **Pris och rabatt**

I fältgruppen **Koncernintern inköpsorder <-> Ursprunglig försäljningsorder** välj följande fält:

- **Kundinformation**
- **RMA-nummer**
- **Batchnummer**
- **Serienummer**

I juridisk person C, på sidan **Koncernintern** för kunder, välj **Försäljningsorderpolicyer**. Välj följande fält i fältgruppen **Skapa koncernintern försäljningsorder**:

- **Försäljningsordernumrering** : **Nummerseriekod**
- **Tillåt samlingsuppdatering av dokument för den ursprungliga kunden**

I fältet **Koncerninterna försäljningsorderpriser** välj följande fält:

- **Pris- och rabattsökning**

I fältgruppen **Koncernintern bokföring av kundfaktura** välj följande fält:

- **Pris per enhet är lika med självkostnad**
- **Initiera bokföring av ursprunglig kundfaktura**

I fältgruppen **Koncernintern försäljningsorder <-> Ursprunglig inköpsorder** välj följande fält:

- **Batchnummer**
- **Serienummer**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
