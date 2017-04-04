---
title: Skapa en avdelning och associera den med avdelningens hierarki
description: "En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation. En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser. Du kan använda avdelningar att rapportera om funktionella områden. Avdelningar kan ha vinst och förlust."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HierarchyDesigner, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ee51abe108b3bc0aabc764b991222db6d185e532
ms.lasthandoff: 03/31/2017


---

# <a name="create-a-department-and-associate-it-with-the-department-hierarchy"></a>Skapa en avdelning och associera den med avdelningens hierarki

En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation. En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser. Du kan använda avdelningar att rapportera om funktionella områden. Avdelningar kan ha vinst och förlust.

En avdelning kan omfatta en grupp kostnadsställen. Positionerna kan tilldelas avdelningar. Klicka för att skapa en avdelning **personal**&gt;**avdelningar**&gt;**avdelning**. I följande tabell beskrivs de fält som är tillgängliga.

| Fält               | Beskrivning                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Namn                | Ange ett namn på avdelningen.                                                                                                                                                                                  |
| Avdelningsnummer   | Ett standardvärde kan genereras automatiskt om en nummersekvens kod tilldelas **organisationsnummer** hänvisning på **nummersekvens** sida.                                                 |
| Söknamn         | Ange ett namn eller en förkortning som kan användas för sökning för avdelningen.                                                                                                                                            |
| Anteckning                | Ange eventuellt ytterligare information här.                                                                                                                                                                            |
| I hierarki        | En vald kryssruta anger att avdelningen ingår i avdelningen hierarki. För information om hur man lägger till en avdelning till avdelning hierarki, se information senare i denna artikel. |
| DUNS-nummer         | DUNS står för Data Universal antal System. Detta är en 9-siffrig kod som är utfärdade av Dun & Bradstreet.                                                                                                     |
| Chef             | Ange den persona som hanterar avdelningen.                                                                                                                                                                    |
| Adresser           | Lägga till adressinformation för avdelningen. Lägg till exempel till postadress till byggnaden där avdelningen finns.                                                                          |
| Kontaktinformation | Lägg till kontaktinformation för avdelningen. Lägg till ett telefonnummer till avdelningens servicedesk, till exempel.                                                                                           |

Om du vill lägga till en avdelning till avdelning hierarki, följ dessa steg.

1.  Klicka på **personal**&gt;**avdelningar**&gt;**avdelningshierarki**.
2.  Klicka på **Redigera**och välj sedan organisationen att avdelningen ska vara.
3.  Klicka på **Infoga**och välj den **avdelning** i listan.
4.  I listan över enheter som visas, välj den avdelning som du vill lägga till i hierarkin.
5.  Spara ändringarna. Du får ett meddelande om att ett utkast av hierarkin har skapats.
6.  När du är klar klickar du på **publicera** i hierarkidesigner. Du kan ange ett giltighetsdatum som anger om hierarkin ska publiceras. Om du exempelvis vill lägga till en ny avdelning i början av nästa kalenderår, ställ in datumet 1 januari på det nya kalenderåret. Ändringarna i hierarkin kommer att träda i kraft den dagen.



