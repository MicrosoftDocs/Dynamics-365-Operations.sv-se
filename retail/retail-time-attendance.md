---
title: Butik tidrapportering
description: "Det här avsnittet beskrivs scenarier som stöds i Microsoft Dynamics 365 för verksamhet – Retail för tid och närvaro."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: eac0b85a17df33c860333c5c19d4fb58f160930f
ms.lasthandoff: 03/31/2017


---

# <a name="retail-time-and-attendance"></a>Butik tidrapportering

Det här avsnittet beskrivs scenarier som stöds i Microsoft Dynamics 365 för verksamhet – Retail för tid och närvaro. 

<a name="manage-worker-setup-and-scheduling"></a>Hantera inställningar för arbetare och schemaläggning
----------------------------------

### <a name="initial-configuration"></a> Ursprunglig konfiguration

-   Kör guiden för konfiguration.
-   Registrera arbetstagare som projekttid arbetstagare.

### <a name="plan-worker-schedules"></a>Planen arbetstagaren scheman

-   Använda profiler med arbete planerare. För mer information, se <Https://technet.microsoft.com/en-us/library/aa551234.aspx>.

För information om konfigurering, se <Https://technet.microsoft.com/en-us/library/aa496971.aspx>.

### <a name="retail-specific-configuration"></a>Retail-specifik konfiguration

-   Aktivera en funktion profil för klocka, för arbetstagare som du vill aktivera tidsregistreringar. Klicka på **POS Funktionsprofiler**&gt;**funktion**&gt;**POS när registreringar**&gt;**aktivera tidsregistreringar**.
-   Konfigurera point of sale (POS) behörigheter grupper att visa timeclock poster tillstånd. Detta tillstånd kan en användare visa tid klocka registreringar av andra arbetstagare i affären (och från alla andra som användaren är kopplad till, via adressboken). Du kanske vill aktivera detta tillstånd för en chef roll men inte för en kassör roll. Klicka på **Kassabehörighetsgrupper**&gt;**visa stämpelklocksregistreringar**.

## <a name="register-time"></a>Kassatid
### <a name="cashier-and-non-cashier-time-registrations"></a>Kassa och icke-kassa tidsregistreringar

-   På POS:
    -   Klocka-operationer:
        -   Logga in med en icke-lådan eller nya skift.
        -   Välj en tid klockan.
        -   Välj önskad funktion:
            -   Instämpling
            -   Avbrott för arbete
            -   Lunchrast
            -   Utstämpling

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Aktuell status</th>
    <th>Tillgängliga funktioner</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Instämpling</td>
    <td><ul>
    <li>Avbrott för arbete</li>
    <li>Lunchrast</li>
    <li>Utstämpling</li>
    </ul></td>
    </tr>
    <tr class="even">
    <td>Avbrott för arbete</td>
    <td>Instämpling</td>
    </tr>
    <tr class="odd">
    <td>Lunchrast</td>
    <td>Instämpling</td>
    </tr>
    <tr class="even">
    <td>Utstämpling</td>
    <td>Instämpling</td>
    </tr>
    </tbody>
    </table>

    [![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)
-   Visa bekräftelsemeddelandet och verifiera att den aktuella aktivitet tid är korrekt.
-   Loggbok:
    -   Klicka på **Loggbok för** att visa tid klockan aktivitet.
    -   Använd filter för att välja olika tidfönster.
    -   Om du arbetar hos flera butiker kan du se din tidsregistreringar från alla butiker där du registrerade tid. Du kan använda butiken filter för att visa tidsregistreringar från en vald butik.

<!-- -->

-   Olika tidszoner:
    -   Om du från en annan plats (för kassören loggbok, eller genom att använda **Visa timeclock poster** för en chef scenario) och platsen är i en annan tidszon, tid som du ser, finnas görat om till din lokala tidzon. Till exempel är en chef för två butiker, i Arizona och den andra Nevada. En kassör registrerar en Stämpla in klockan 09:00 I Arizona. I det ögonblicket i Nevada är 08.00. Därför, om du är i Nevada lagra och titta på gång inskrivningurkunder, projekttid är markerade som 08.00

## <a name="view-worker-time-registrations"></a>Visa tidsregistreringar för arbetare
### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Visa arbetstagaren tidsregistreringar och filtrera genom butik eller aktivitetstyp

På POS:

-   Välj **Visa timeclock poster**.
-   Du ser tid klocka registrering verksamheter från alla anställda som är tilldelade till samma butiker som du tilldelats.
-   Du kan använda aktivitetstyp och lagra filter för att filtrera på tidsregistreringar.

## <a name="process-and-manage-time-registrations"></a>Bearbeta och hantera tidsregistreringar
En Dynamics 365 för verksamhet – Retail användare följer arbetsflödet om du vill beräkna, godkänna och överföra tidsregistreringar till lönesystemet.

### <a name="primary-operations"></a>Primära verksamheter

-   Beräkna
-   Godkänn
-   Skicka till lönesystem

### <a name="other-common-operations"></a>Andra gemensamma åtgärder

-   Bulk klocka-ut
-   Registrera frånvaro

För mer information om hur tid och uppslutning registreringar, se <Https://technet.microsoft.com/en-us/library/aa573180.aspx>.

