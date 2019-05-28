---
title: Tids- och närvarohantering i Retail
description: Det här avsnittet beskriver scenarierna som stöds för tids- och närvarohantering i detaljhandel i Microsoft Dynamics 365 for Retail.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 4c54909a02376a62a72a986e634649fa0ae54284
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567963"
---
# <a name="time-and-attendance-management-in-retail"></a>Tids- och närvarohantering i Retail

[!include [banner](includes/banner.md)]

Det här avsnittet beskriver scenarierna som stöds för tids- och närvarohantering i detaljhandel i Microsoft Dynamics 365 for Retail.

## <a name="manage-worker-setup-and-scheduling"></a>Hantera inställningar för arbetare och schemaläggning

### <a name="initial-configuration"></a> Ursprunglig konfiguration

- Kör guiden för konfiguration.
- Registrera arbetstagare som projekttid arbetstagare.

### <a name="plan-worker-schedules"></a>Planen arbetstagaren scheman

- Använda profiler med arbete planerare. Mer information finns i [Använd profiler med arbetsplanering](https://technet.microsoft.com/library/aa551234.aspx).

Mer information om konfigurationsstegen finns i [inställning av tid och närvaro](https://technet.microsoft.com/library/aa496971.aspx).

### <a name="retail-specific-configuration"></a>Retail-specifik konfiguration

- Aktivera en funktion profil för klocka, för arbetstagare som du vill aktivera tidsregistreringar. Klicka på **Kassafunktionsprofiler** &gt; **Funktioner** &gt; **Tidsregistreringar vid kassa** &gt; **Aktivera tidsregistreringar**.
- Konfigurera point of sale (POS) behörigheter grupper att visa timeclock poster tillstånd. Detta tillstånd kan en användare visa tid klocka registreringar av andra arbetstagare i affären (och från alla andra som användaren är kopplad till, via adressboken). Du kanske vill aktivera detta tillstånd för en chef roll men inte för en kassör roll. Klicka på **Kassabehörighetsgrupper** &gt; **Visa stämpelklocksregistreringar**.

## <a name="register-time"></a>Kassatid

### <a name="cashier-and-non-cashier-time-registrations"></a>Kassa och icke-kassa tidsregistreringar

- På POS:

    - Klocka-operationer:

        - Logga in med en icke-lådan eller nya skift.
        - Välj en tid klockan.
        - Välj önskad funktion:

            - Instämpling
            - Avbrott för arbete
            - Lunchrast
            - Utstämpling

        <table>
        <thead>
        <tr>
        <th>Aktuell status</th>
        <th>Tillgängliga funktioner</th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td>Instämpling</td>
        <td>
        <ul>
        <li>Avbrott för arbete</li>
        <li>Lunchrast</li>
        <li>Utstämpling</li>
        </ul>
        </td>
        </tr>
        <tr>
        <td>Avbrott för arbete</td>
        <td>Instämpling</td>
        </tr>
        <tr>
        <td>Lunchrast</td>
        <td>Instämpling</td>
        </tr>
        <tr>
        <td>Utstämpling</td>
        <td>Instämpling</td>
        </tr>
        </tbody>
        </table>

        [![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)

- Visa bekräftelsemeddelandet och verifiera att den aktuella aktivitet tid är korrekt.
- Loggbok:

    - Klicka på **Loggbok för** att visa tid klockan aktivitet.
    - Använd filter för att välja olika tidfönster.
    - Om du arbetar hos flera butiker kan du se din tidsregistreringar från alla butiker där du registrerade tid. Du kan använda butiken filter för att visa tidsregistreringar från en vald butik.

- Olika tidszoner:

    - Om du från en annan plats (för kassören loggbok, eller genom att använda **Visa timeclock poster** för en chef scenario) och platsen är i en annan tidszon, tid som du ser, finnas görat om till din lokala tidzon. Du är till exempel chef för två butiker, en i Arizona och den andra i Nevada. En kassör registrerar en instämpling klockan 09:00 i Arizona. I det ögonblicket i Nevada är 08.00. Därför, om du är i Nevada lagra och titta på gång inskrivningurkunder, projekttid är markerade som 08.00

## <a name="view-worker-time-registrations"></a>Visa arbetstidsregistrering

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Visa arbetstagaren tidsregistreringar och filtrera genom butik eller aktivitetstyp

På POS:

- Välj **Visa timeclock poster**.
- Du ser tid klocka registrering verksamheter från alla anställda som är tilldelade till samma butiker som du tilldelats.
- Du kan använda aktivitetstyp och lagra filter för att filtrera på tidsregistreringar.

## <a name="process-and-manage-time-registrations"></a>Bearbeta och hantera tidsregistreringar

En Dynamics 365 for Retail-användare följer arbetsgången för att beräkna, godkänna och överföra tidsregistreringar till lönesystemet.

### <a name="primary-operations"></a>Primära verksamheter

- Beräkna
- Godkänn
- Skicka till lönesystem

### <a name="other-common-operations"></a>Andra gemensamma åtgärder

- Bulk klocka-ut
- Registrera frånvaro

Läs mer om hur du bearbetar registreringar för tid och närvaro i [Bearbeta registreringar för tid och närvaro](https://technet.microsoft.com/library/aa573180.aspx).
