---
title: Skapa avdelningar och inkludera dessa i avdelningshierarkin
description: En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation. En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser. Du kan använda avdelningar att rapportera om funktionella områden. Avdelningar kan ha vinst och förlust.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HierarchyDesigner, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 723e46f98545e80551da9f79b6aeffc3eca48830
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466024"
---
# <a name="create-departments-and-include-them-in-the-department-hierarchy"></a>Skapa avdelningar och inkludera dessa i avdelningshierarkin

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En avdelning är en driftenhet som representerar en kategori eller verksamhetsområde inom en organisation. En avdelning är ansvarig för en viss del av organisationen, såsom försäljning, bokföring eller mänskliga resurser. Du kan använda avdelningar att rapportera om funktionella områden. Avdelningar kan ha vinst och förlust.

En avdelning kan omfatta en grupp kostnadsställen. Positionerna kan tilldelas avdelningar. Klicka på **Personal** &gt; **Avdelningar** &gt; **Avdelning**. Följande register beskriver de fält som är tillgängliga.

| Fält               | Beskrivning                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Namn                | Ange ett namn på avdelningen.                                                                                                                                                                                  |
| Avdelningsnummer   | Ett standardvärde kan skapas automatiskt om en nummersekvens kod tilldelas **organisationsnummer** hänvisning på **nummersekvens** sida.                                                 |
| Söknamn         | Ange ett namn eller en förkortning som kan användas för sökning för avdelningen.                                                                                                                                            |
| Anteckning                | Ange eventuellt ytterligare information här.                                                                                                                                                                            |
| I hierarki        | En vald kryssruta anger att avdelningen ingår i avdelningen hierarki. För information om hur man lägger till en avdelning till avdelning hierarki, se information senare i denna artikel. |
| DUNS-nummer         | DUNS står för Data Universal antal System. Detta är en 9-siffrig kod som är utfärdade av Dun & Bradstreet.                                                                                                     |
| Chef             | Ange den persona som hanterar avdelningen.                                                                                                                                                                    |
| Adresser           | Lägga till adressinformation för avdelningen. Lägg till exempel till postadress till byggnaden där avdelningen finns.                                                                          |
| Kontaktinformation | Lägg till kontaktinformation för avdelningen. Lägg till ett telefonnummer till avdelningens servicedesk, till exempel.                                                                                           |

Om du vill lägga till en avdelning till avdelning hierarki, följ dessa steg.

1.  Klicka **Personal** &gt; **Avdelningar** &gt; **Avdelningshierarki**.
2.  Klicka på **Redigera** och välj sedan organisationen att avdelningen ska vara.
3.  Klicka på **Infoga** och välj den **avdelning** i listan.
4.  I listan över enheter som visas, välj den avdelning som du vill lägga till i hierarkin.
5.  Spara ändringarna. Du får ett meddelande om att ett utkast av hierarkin har skapats.
6.  När du är klar klickar du på **Publicera** i hierarkidesignern. Du kan ange ett giltighetsdatum som anger när hierarkin ska publiceras. Om du exempelvis vill lägga till en ny avdelning i början av nästa kalenderår, ställ in datumet 1 januari på det nya kalenderåret. Ändringarna i hierarkin kommer att träda i kraft den dagen.

## <a name="steps-for-creating-a-department"></a>Steg för att skapa en avdelning
Hänvisa till ämnet [Definiera nya avdelningar](../fin-and-ops/hr/tasks/define-new-departments.md) för stegvisa anvisningar om hur du skapar en ny avdelning. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]