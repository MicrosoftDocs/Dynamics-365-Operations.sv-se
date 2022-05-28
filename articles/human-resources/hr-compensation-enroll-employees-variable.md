---
title: Registrera en medarbetare i en variabel kompensationsplan
description: Chefen över kompensationer och förmåner kan anmäla medarbetare till variabla kompensationsplaner att beräkna kontanta eller icke-kontanta ersättningar för medarbetare.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11f86bfa4bfcece164755bb5d86944e0bed0fff2
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692294"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>Registrera en medarbetare i en variabel kompensationsplan


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Chefen över kompensationer och förmåner kan anmäla medarbetare till variabla kompensationsplaner att beräkna kontanta eller icke-kontanta ersättningar för medarbetare. I den här proceduren förutsätts att en variabel kompensationsplan har skapats med fältet **Aktivera anmälan** inställt på **Ja**, och att berättiganderegler har skapats för den variabla kompensationsplanen. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Gå till **Personal** > **Arbetare** > **Medarbetare** > **Kompensation** > **Registrering i variabel plan**.

1. Klicka på **Ny**.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Plan**.
    * Planuppslagningen filtreras för att visa endast de variabla kompensationsplaner som medarbetaren är berättigad till baserat på berättiganderegler.  
3. Klicka på länken på den valda raden i listan.
4. Växla utökningen av avsnittet **Allmänt**.
5. Ange ett datum i fältet **Giltighetsdatum**.
6. Klicka på **Spara**.
7. Växla visningen av avsnittet **Åsidosättningar**.
    * Du kan också välja ett anställningsregeldatum för att åsidosätta anställningsdatumet för en medarbetare när anställningsregeln som har angetts för den valda variabla planen är Procent.  
    * Om den variabla planen är en procentsats av basplanen kan ersättningsprocenten åsidosättas för medarbetaren. Om den variabla kompensationsplanen är en plan med antal enheter kan antalet enheter åsidosättas för medarbetaren.  
    * Om medarbetaren ska få ett fast belopp i belöning, kan beloppet anges här.  
8. Växla visningen av avsnittet **Organisationsåsidosättningar**.
    * Om hänsyn ska tas till medarbetarens resultat, resultat för olika avdelningar eller för en annan avdelning än den som har tilldelats till medarbetarens befattning kan avdelningen åsidosättas. Kolumnen **Procent** ska uppgå till 100.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
