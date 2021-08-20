---
title: Skapa en arbetsgrupp för legotillverkning för lean manufacturing
description: Om du vill modellera legotillverkningsarbete för lean manufacturing måste du skapa en arbetsgrupp som är kopplad till den leverantör som tillhandahåller arbetet.
author: cvocph
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acb0adf3e53830f951ae6d1faefd3f30aa3a445e28dc1a08b76a408bdf9af810
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744688"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a>Skapa en arbetsgrupp för legotillverkning för lean manufacturing

[!include [banner](../../includes/banner.md)]

Om du vill modellera legotillverkningsarbete för lean manufacturing måste du skapa en arbetsgrupp som är kopplad till den leverantör som tillhandahåller arbetet. En arbetsgrupp för legotillverkning är kopplad till leverantören genom associationen med en resurs av typen Leverantör. Om du spelar upp den här inspelningen i demonstrationsföretaget USMF kan du välja leverantörskonto-ID 1002 och plats 1.


## <a name="create-a-vendor-resource"></a>Skapa en leverantörsresurs
1. Gå till Resurser.
2. Klicka på Ny.
3. Ange ett värde i fältet Resurs.
4. Ange ett värde i fältet Beskrivning.
5. Välj Leverantör i fältet Typ.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantör.

## <a name="create-the-resource-group"></a>Skapa resursgruppen
1. Gå till Resursgrupper.
2. Klicka på Ny.
3. Skriv ett värde i fältet Resursgrupp.
4. Ange ett värde i fältet Beskrivning.
5. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
    * Välj den plats som arbetsgruppen ska tilldelas till. I teorin kan en plats representera en enskild plats som drivs av en leverantör. Men i de flesta fall allokeras resurser på entreprenad bara till den plats som beställer entreprenadarbetet. Observera att inkommande och utgående lagerställen för arbetsgrupper för legotillverkning måste finnas på samma plats.  
6. Ange ett värde i fältet Plats.
7. @SysTaskRecorder:_RequestClose
8. Markera eller avmarkera kryssrutan Arbetsgrupp.
9. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Inleveranslagerställe.
    * Välj lagerstället och platsen som används för att mellanlagra materialet för arbetsgruppen som hanteras av leverantören. I de flesta fall modelleras lagerstället och platsen genom att använda ett separat lagerställe per leverantör och ett lagerställe per arbetsgrupp.  
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plats för inleverans.
11. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Utleveranslagerställe.
    * Ange lagerstället och platsen där materialet bokförs när arbetsgruppens legotillverkningsaktiviteter bokförs. Lagerstället och platsen kan finnas på leverantörens plats om leverantören rapporterar kanban-jobb. Alternativt kan vara lagerstället och platsen vara inleveransplatsen som hör till nästa steg i produktionsflödet.  
12. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Utleveransplats.
13. Utöka eller komprimera avsnittet Kalendrar.
14. Klicka på Lägg till.
15. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kalender.
    * Associera arbetsgruppens arbetstidskalender till resursgruppen. För viktiga resurser rekommenderar vi att du definierar specifika kalendrar som motsvarar exakta arbetstider och relaterade kapaciteter för arbetsgrupp eller leverantörsplats.  
16. Expandera eller komprimera avsnittet Resurser.
17. Klicka på Lägg till.
    * En legotillverkningsresursgrupp måste ha en associerad resurs av typen Leverantör som länkar resursgruppen till leverantörskontot.  
18. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Resurs.
    * Välj eller ange leverantörsresursen som du skapade i föregående underuppgift.  
19. Expandera eller komprimera avsnittet Kapacitet för arbetsgrupp.
20. Klicka på Lägg till.
    * En arbetsgrupp måste ha en definierad kapacitet. I det här exemplet ska vi skapa en genomflödeskapacitet på 100 stycken per vanlig arbetsdag.  
21. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Produktionsflödesmodell.
22. Markera ett alternativ i fältet Kapacitetsperiod.
23. Ange ett värde i fältet Genomsnittlig genomflödeskvantitet.
24. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Enhet.
25. ResolveChanges enheten.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]