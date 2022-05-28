---
title: Ställ in kompensationsrutnät
description: Kompensationsrutnät används för att definiera och underhålla lönstrukturerna för fasta kompensationsplaner.
author: twheeloc
ms.date: 01/03/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9119c15cf80b9ebb9bed83ac438f24249aa4aa2f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691685"
---
# <a name="set-up-compensation-grids"></a>Ställ in kompensationsrutnät


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Kompensationsrutnät används för att definiera och underhålla lönstrukturerna för fasta kompensationsplaner. Kompensationsrutnät kan delas mellan flera planer och kopieras när du skapar en ny kompensationsplan.  Innan du skapar ett kompensationsrutnät måste nivåer och referenspunkter ställas in. I det här exemplet skapas en ny typ av kompensationsrutnät med hjälp av demodata för nivåer och referenspunkter. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="set-up-information-about-the-compensation-grid"></a>Ställ in information om kompensationsrutnätet
1. Gå till **Personal** > **Kompensation** > **Fast kompensation** > **Kompensationsrutnät**.
2. Klicka på **Ny**.
3. Ange ett värde i fältet **Rutnät**.
4. I fältet **Beskrivning** anger du ett värde.
5. Välj ett alternativ i fältet **Typ**.
6. Ange eller välj ett värde i fältet **Referensinställningar**.
7. Ange eller välj ett värde i fältet **Valuta.**
8. Ange ett datum i fältet **Giltighetsdatum**.

## <a name="add-levels-to-the-compensation-structure"></a>Lägg till nivåer i kompensationsstrukturen
1. Klicka på **Kompensationsstruktur**.
2. Markera vald rad i listan.
3. Ange eller välj ett värde i fältet **Nivå**.
4. Klicka på **Ny**.
5. Markera vald rad i listan.
6. Ange eller välj ett värde i fältet **Nivå**.
7. Klicka på **Ny**.
8. Markera vald rad i listan.
9. Ange eller välj ett värde i fältet **Nivå**.
10. Klicka på **Ny**.
11. Markera vald rad i listan.
12. Ange eller välj ett värde i fältet **Nivå**.
13. Klicka på **Ny**.
14. Markera vald rad i listan.
15. Ange eller välj ett värde i fältet **Nivå**.

## <a name="fill-in-the-compensation-structure-with-values"></a>Fyll i kompensationsstrukturen med värden
1. Markera vald rad i listan.
    * Nu kan kompensationsvärden anges manuellt i varje fält i registret, eller också kan massändringsfunktionen användas för att fylla i flera fält och utför grundläggande beräkningar.  
2. Klicka på **Massändra**.
    * I det här rutnätet använder vi först värdet på mittpunkten på den första nivån till alla fält i registret. Detta blir basen för kompensationsmatrisen.  
3. Välj ett alternativ i fältet **Modifieringstyp**.
4. Ange ett tal i fältet **Justeringsbelopp**.
5. Markera eller avmarkera alla rader i listan.
6. Klicka på **Använd i rutnät**.
    * Nu använder massändringsfunktionen för att öka beloppen på varje efterföljande nivå med en viss procentandel eller ett visst belopp. I det här exemplet ska varje grad ha en spridning på 12,5 % mellan mittpunkterna.  
7. Välj ett alternativ i fältet **Modifieringstyp**.
8. Ange ett tal i fältet **Justeringsbelopp**.
9. Hitta och markera önskad post i listan.
10. Klicka på **Använd i rutnät**.
    * Nu använder vi massändringsfunktionen för att de lägsta och högsta referenspunkterna för varje nivå. I det här exemplet använder vi en spridning på 50 %, så den lägsta referenspunkten justeras med -20 %, och den högsta med +20 %.  
11. Ange ett tal i fältet **Justeringsbelopp**.
12. Ange eller välj ett värde i fältet **Referenspunkt**.
13. Markera eller avmarkera alla rader i listan.
14. Klicka på **Använd i rutnät**.
15. Ange ett tal i fältet **Justeringsbelopp**.
16. Ange eller välj ett värde i fältet **Referenspunkt**.
17. Markera eller avmarkera alla rader i listan.
18. Klicka på **Använd i rutnät**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
