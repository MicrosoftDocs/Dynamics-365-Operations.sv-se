---
title: Jobbet Rensning av behållningsposter för distributionslagerhantering
description: Denna artikel beskriver rensningsjobbet för lagerbehållningen, vilket förbättrar systemets prestanda genom att identifiera och ta bort relaterade poster som inte behövs.
author: perlynne
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: a82a3b26f2bf7cb546383da047d18c2997569ca5
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065162"
---
# <a name="warehouse-management-on-hand-entries-cleanup-job"></a>Rensningsjobb för lagerbehållningsposter för lagerställe

[!include [banner](../includes/banner.md)]

Prestanda för frågor som används för att beräkna lagerbehållning påverkas av antalet poster i registren som ingår. Ett sätt att förbättra prestandan är att minska antalet poster som måste beaktas i databasen.

Denna artikel beskriver rensningsjobbet för lagerbehållningen, vilket innebär att poster som inte behövs i tabellerna `InventSum` och `WHSInventReserve` tas bort. Dessa register lagrar behållningsinformation för artiklar som aktiveras för bearbetning av lagerstyrning. (Dessa objekt kallas WMS-artiklar). Om du tar bort dessa poster kan du förbättra prestanda för lagerbehållningen avsevärt.

## <a name="what-the-cleanup-job-does"></a>Vad rensningsjobbet gör

Rensningsjobbet för lagerbehållningen tar bort alla poster i tabellerna `WHSInventReserve` och `InventSum` där alla fältvärden är *0* (noll). Dessa poster kan tas bort eftersom de inte bidrar till behållningsinformationen. Jobbet tar bara bort poster som finns under nivån **lagerställe**.

Om du tillåter negativa fysiska lager kan det hända att rensningsjobbet inte kan ta bort alla relevanta poster. Orsaken till den här begränsningen är att jobbet måste tillåtas för ett särskilt scenario där en ID-nummer har flera löpnummer och ett av dessa löpnummer har blivit negativt. Systemet har till exempel noll i behållning på ID-nummernivå när ett ID-nummer har + 1 dator med löpnummer 1 och – 1 dator med löpnummer 2. För det här speciella scenariot tar jobbet en första bredd, där det försöker ta bort från lägre nivåer först.

## <a name="schedule-and-configure-the-cleanup-job"></a>Schemalägga och konfigurera rensningsjobbet

Rensningsjobbet för bokföring av lagerbehållning finns tillgängligt för **lagerhantering \> periodiska uppgifter \> rensa \> rensningsjobb för lagerbehållningsposter för lagerställe**. Använd standardjobbinställningarna om du vill styra omfång och schema för körning av jobbet. Dessutom finns följande inställningar:

- **Ta bort om detta inte är uppdaterat för så här många dagar** – Ange det minsta antal dagar som jobbet ska vänta innan en behållningstransaktion med kvantiteten på noll raderas. Använd den här inställningen för att minska risken för borttagning av behållningsposter som fortfarande används. Om du vill att rensningen ska ske så snart som möjligt anger du antingen *0* (noll) eller lämnar fältet tomt.
- **Maximal körningstid (timmar)** – Ange rensningsjobbets maximala körningstid, i timmar. Om jobbet inte slutförs före den här tiden sparas det arbete som har utförts hittills och sedan stängs det. Den här funktionen är särskilt relevant för implementeringar med hög lageranvändning. I dessa fall bör du schemalägga jobbet så att det körs vid tillfällen när systembelastningen är så ljus som möjligt. Om du vill att batchjobbet ska fortsätta köras tills det är slutfört anger du *0* (noll) eller låter fältet vara tomt. Den här inställningen är endast tillgänglig om den relaterade funktionen har [Aktiverats i systemet](#max-execution-time).

Även om du kan köra jobbet under normala kontorstider rekommenderar vi att du kör det utanför arbetstiden. På så sätt undviker du konflikter som kan uppstå om en användare arbetar med en post som också rensas.

Om jobbet försöker ta bort en post för en artikel medan den posten används av en annan användare uppstår ett dödläge för antingen rensningsjobbet eller användaren.

När jobbet körs har det en genomförande storlek på 100. Med andra ord görs ett försök att genomföra en gång för varje 100 borttagning. Eftersom vissa borttagningar har ställts in, kan det emellertid finnas situationer där fler än 100 poster kan tas bort i samma transaktion. Därför kan låsning av eskaleringar ändå uppstå ibland.

## <a name="possible-user-impact"></a>Möjlig användarpåverkan

Användare kan påverkas om rensningsjobbet för behållningstransaktioner tar bort alla poster för en viss nivå (t.ex. ID-nummernivå). I det här fallet kanske funktionen för att se att lagret tidigare var tillgängligt på en ID-numret inte fungerar som förväntat, eftersom de relevanta behållningsposterna inte längre är tillgängliga. Detta kan till exempel upplevas i följande situationer:

- I **Behållningslista**, när användaren avmarkerar villkoret **Kvantitet \<\> 0** eller väljer villkoret **Stängda transaktioner** i inställningarna **Dimensionsvisning**.
- I en rapport **Fysiskt lager per lagerdimension** för tidigare perioder när användaren konfigurerar parametern **från och med datum**.

Den prestandaförbättring som rensningsjobbet tillhandahåller bör dock göra att dessa små förluster i funktionen förbättras.

## <a name="make-the-maximum-execution-time-setting-available"></a><a name="max-execution-time"></a>Gör inställningen för maximal körningstid tillgänglig

Inställningen **Maximal körningstid** är bara tillgänglig *Maximal körningstid för jobbet Rensning av behållningsposter för lagerstyrning* av jobb är aktiverad. Från och med version 10.0.25 av Supply Chain Management är denna funktion aktiverad som standard. Administratörer kan aktivera eller inaktivera den här funktionen genom att söka efter *Maximal körningstid för jobbet Rensning av behållningsposter för lagerstyrning* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]