---
title: Skalningsenheter i en distribuerad hybridtopologi
description: Detta ämne ger information, se moln och kantskalningsenhet med arbetsbelastning för tillverkning och distributionslagerstyrning.
author: Mirzaab
ms.date: 04/22/2021
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5ec846b294cd9ca62ff15a5306e012813c77e306
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676363"
---
# <a name="scale-units-in-a-distributed-hybrid-topology"></a>Skalningsenheter i en distribuerad hybridtopologi

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Kapaciteten för skalningsenhet för Microsoft Dynamics 365 Supply Chain Management har gjorts tillgänglig för dig enligt de villkor som styr användningen av tjänsten. Mer information finns i [Juridisk information för Microsoft Dynamics](https://go.microsoft.com/fwlink/?LinkID=290927).
>
> Genom att aktivera moln- och kantskalningsenheter bekräftar du att du förstår att vissa data som är relaterade till konfigurationen och bearbetningen av moln- och kantskalningsenheter kan lagras i ett datacenter som finns i USA. Mer information om databearbetning för molnbaserade enheter och kantskalningsenheter finns i avsnittet [Databehandling i samband med hantering av skalningsenheter](#data-processing-management) längre fram i det här avsnittet.

## <a name="core-value-proposition-for-a-distributed-hybrid-topology"></a>Grundvärdesförslag för en distribuerad hybridtopologi

Företag som arbetar med tillverkning och distribution måste kunna köra viktiga affärsprocesser dygnet runt, utan avbrott och i skala. Med en distribuerad hybridtopologi kan företag köra viktiga verksamhetskritiska tillverknings- och lagerprocesser utan avbrott, även om de är i har tillfälliga nätverksanslutnings- eller latensproblem.

En distribuerad hybridtopologi introducerar begreppet *skalningsenehter*, som gör det möjligt att distribuera arbetsbelastningar för verkstad och lagerställe mellan olika miljöer. Med hjälp av den här funktionen kan du förbättra prestanda, förhindra avbrott i tjänsten och maximera drifttiden. Saklningsenheter tillhandahålls via följande tillägg för din Supply Chain Management-prenumeration:

- Tillägg för molnskalningsenhet för Dynamics 365 Supply Chain Management
- Tillägg för kantskalningsenhet för Dynamics 365 Supply Chain Management

Arbetsbelastningsfunktionerna frisläpps kontinuerligt genom stegvisa förbättringar.

## <a name="scale-units-and-dedicated-workloads"></a>Skalningsenheter och dedikerade arbetsbelastning

Skalningsenheter utökas med Supply Chain Management navmiljö genom att lägga till dedikerad bearbetningskapacitet. Skalningsenheter kan köras i molnet. De kan också köras ["on the edge"](cloud-edge-edge-scale-units-lbd.md), på plats på din lokala anläggning.

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 med skalningsenheter.":::

Skalningsenheter tillhandahåller effektivitet, tillförlitlighet och skalning för de tilldelade arbetsbelastningarna. Kantskalenheter kan tillfälligt kopplas ned från den molnbaserade miljön, och medarbetarna fortsätter att arbeta i de tilldelade arbetsbelastningarna "on the edge" – i utkanten av nätverket istället för som annars centralt.

En *arbetsbelastning* är en definierad uppsättning affärsfunktioner som kan beaktas och delegeras till en skalningsenhet. Trots att arbetsbelastningen för Warehouse management har frisläppts befinner sig arbetsbelastningen för tillverkningskörning fortfarande i förhandsgranskningsstadiet.

Du kan använda [portalen för skalningsenhetsansvarig](https://sum.dynamics.com) för att konfigurera din navmiljö och dina molnskalningsenhet för utvalda arbetsbelastningar. Du kan också tilldela flera arbetsbelastningar per skalningsenhet. Mer information om förutsättningar och begränsningar för molnbaserade skalningsenheter i den aktuella versionen finns i avsnittet [Förutsättningar och begränsningar för molnskalningsenheter](#cloud-scale-unit-prerequisites) längre fram i detta ämne.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Särskilda arbetsbelastningsmöjligheter för distributionslagerstyrning i en skalningsenhet

Arbetsbelastningen för lagerstyrning gör det möjligt för dina lagerställeåtgärder att anpassa och köra i en miljö med underhåll som inte är underhåll, genom att använda enstaka underhållsfönster. Arbetsbelastningen för lagerstyrning har stöd för de flesta hanteringsprocesserna för lagerställen i företag. För mer information, se [Arbetsbelastningar för hantering av distributionslager för moln- och kantskalningsenheter](cloud-edge-workload-warehousing.md).

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Särskilda arbetsbelastningsmöjligheter för tillverkningskörning i en skalningsenhet

Tillverkningsarbetsbelastningen har följande funktioner:

- Maskinoperatörer och arbetsledare kan komma åt den operationella produktionsplanen.
- Maskinoperatörer kan hålla planen aktuell genom att köra separata jobb för bearbetning och processtillverkning.
- Arbetsledaren kan justera driftsplanen.
- Arbetare kan få åtkomst till tid och närvaro för in- och utstämpling "on the edge" – i utkanten av nätverket istället för som annars centralt – detta för att säkerställa korrekt löneberäkning för medarbetarna.

För mer information, se [Arbetsbelastningar för tillverkningskörning för moln- och kantskalningsenheter](cloud-edge-workload-manufacturing.md).

## <a name="considerations-before-you-enable-the-distributed-hybrid-topology-for-supply-chain-management"></a>Att tänka på innan du aktiverar distribuerad hybridtopologi för Supply Chain Management

Genom att aktivera den distribuerade hybridtopologin överför du din molnbaserade Supply Chain Management-miljö så att den fungerar som ett nav. Du kan också associera ytterligare miljöer som konfigureras som skalningsenheter i molnet eller "on the edge" – i utkanten av nätverket istället för som annars centralt.

### <a name="prerequisites-and-limitations-for-cloud-scale-units"></a><a name="cloud-scale-unit-prerequisites"></a>Förutsättningar och begränsningar för molnskalningsenheter

I den aktuella versionen för skalningsenheter är vissa funktioner ännu inte tillgängliga, men kan komma att läggas till i stegvisa versioner med tiden.

#### <a name="you-must-be-a-licensed-customer-of-supply-chain-management"></a>Du måste vara licenskund i Supply Chain Management

Du måste ha en licens för Supply Chain Management för att kunna registrera dig för distribuerade topologin. Din befintliga molnbaserade miljö kommer att bli navet i din topologi. Du kan deklarera både sandbox- och produktionsmiljöerna som navmiljöer, och du kan lägga till skalningsenheter enligt de tillägg som du skaffar.

#### <a name="your-existing-project-must-be-administered-via-the-global-commercial-version-of-lcs"></a>Ditt befintliga projekt måste administreras via den globala handelsversionen av LCS

Ditt befintliga Microsoft Dynamics Lifecyle Services-projekt (LCS) måste uppfylla följande versionskrav:

- Projektet måste administreras via den globala handelsversionen av LCS, som finns på [lcs.dynamics.com](https://lcs.dynamics.com).
- Lokala versioner av LCS (såsom [eu.lcs.dynamics.com](https://eu.lcs.dynamics.com) och [fr.lcs.dynamics.com](https://fr.lcs.dynamics.com)) stöds inte.
- Myndighetsversioner av LCS stöds inte.
- Det går inte att använda den version av LCS som finns.

#### <a name="your-current-production-environment-must-be-of-the-self-service-type-in-lcs"></a>Din aktuella produktionsmiljö måste vara av självbetjäningstyp i LCS

Din aktuella produktionsmiljö måste vara taggad med typen **Självbetjäning** i LCS. Denna typ anger att klientinnehavaren i ditt LCS-projekt redan har konverterats till att stödja värdmodellen Azure Service Fabric.

> [!IMPORTANT]
> Miljötyper som körs som infrastruktur som en tjänst (IaaS) stöds inte. Dessa miljöer är vanligtvis taggade med typen **Hanteras av Microsoft** i LCS. Om du har miljöer av den här typen bör du arbeta tillsammans med din Microsoft-kontakt i syfte att förstå tidslinjen för migrering till typen **Självbetjäning**.

Microsoft arbetar med att överföra alla molnbaserade miljöer inom Supply Chain Management från en IaaS-modell till en topologi som finns i Service Fabric. Denna flytt ger en större skalbarhet och gör servicehanteringen enklare. Därför går det snabbare att distribuera och underhålla åtgärder. Servicekomponenter migreras på samma sätt till begreppet mikrotjänster, och värdmodellen för tjänsten kommer att [övergå](/virtualization/windowscontainers/about/containers-vs-vm) från en virtuell maskinmodell (VM) till en lättare containerarkitektur.

I slutändan kommer samma Service Fabric-baserade containerinfrastruktur för tjänster att driva såväl molnbaserade som kantinstanser av tjänsten, oavsett om en instans är ett nav i molnet eller en skalningsenhet i molnet eller "on the edge" – i utkanten av nätverket istället för som annars centralt.

Innan du kan ta steget över till den hybridtopologi som stöder skalningsenheter måste projektets klientorganisation överföras till modellen med Service Fabric som värd. Alla miljöer som fungerar som nav måste dessutom konverteras.

> [!TIP]
> Om du vill fråga om statusen för din klientorganisation för LCS-projekt kan du söka efter din typ av miljö i [LCS](https://lcs.dynamics.com/) eller kontakta din partner eller din Microsoft-kontakt.

#### <a name="local-business-data-on-premises-environments-arent-supported-as-hubs-for-scale-units"></a>Lokala företagsdatamiljöer (lokalt) stöds inte som nav för skalningsenheter

Lokala miljöer kan inte fungera som nav för skalningsenheter. Navmiljöer måste alltid vara molnbaserade.

#### <a name="scale-unit-management-capabilities-are-limited"></a>Funktionerna för hantering av skalningsenheter är begränsade

Hanteringsfunktionerna som kan hjälpa till med förflyttning av arbetsbelastningar är begränsade. Vissa hanteringsåtgärder stöds inte för självbetjäning, och du kan komma att behöva begära stöd via din partner eller Microsoft-kontakt. Du kan till exempel ta med vissa förflyttningar av arbetsbelastning mellan skalningsenheter och tillfälliga ad-hoc-förflyttningar i katastrofscenarion.

#### <a name="metrics-and-measurements-arent-yet-available"></a>Mätvärden och mått är ännu inte tillgängliga

Mätvärden och mått som kan hjälpa dig att välja det bästa programmet för dina skalningsenheter är ännu inte tillgängliga. Arbeta tillsammans med din kontaktperson eller implementerings partner på Microsoft för att välja det bästa programmet.

### <a name="data-processing-during-management-of-scale-units"></a><a name="data-processing-management"></a>Databehandling vid hantering av skalningsenheter

När du aktiverar din Dynamics 365-miljö för att stödja distribuerad hybridtopologi för molnbaserade enheter och kantskalningsenheter, kommer vissa hanteringstjänster bara att lagras med värdar baserade i USA, som för LCS. Detta beteende påverkar överföringen och lagringen av viss administrativ information och konfigurationsinformation som används i [portalen för skalningsenhetsansvarig](https://sum.dynamics.com). Nedan följer några exempel:

- Namn och ID för innehavare
- Ditt LCS projekt-ID
- E-postadresser för administratör och projektägare som används för inloggning
- Miljö-ID för nav- och skalningsenheter
- Arbetsbelastningskonfigurationer, inklusive namn och fysiska adresser för juridiska personer och lokaler, så att din topologi kan visas på en geografisk karta
- Insamlade mått (t.ex. svarstid och dataflöde) som visas på analyssidan för kartan i syfte att hjälpa dig att välja den bästa användningen av dina skalningsenheter

Data som överförs till och lagras i de amerikanska datacentren kommer att raderas i enlighet med datalagringsprinciperna från Microsoft. Din integritet är viktig för Microsoft. Mer information finns i vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=521839).

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>Registrera dig för den distribuerade hybridtopologin för Supply Chain Management

### <a name="try-out-the-distributed-hybrid-topology"></a>Prova en distribuerad hybridtopologi

Registreringsprocessen för distribuerad hybridtopologi sker i två steg. Under den första fasen bör du [prova](cloud-edge-try-out.md) lösningen och validera dina anpassningar i syfte att säkerställa att dessa fungerar i en distribuerad topologi som omfattar skalningsenheter. (Du kan använda befintliga utvecklingsmiljöer för att validera.) Du kan sedan fortsätta till det andra steget, där du skaffar produktionsmiljöer.

## <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>Välj klientorganisationen för LCS-projekt samt detaljerad registreringsprocess

Skalningsenheter ges i flera lagerhållningsenheter (SKU) och prissättningsalternativ. Därför kan du välja det alternativ som bäst uppfyller dina krav på volym och prestanda för planerade månatliga transaktioner.

> [!TIP]
> Identifiera den storlek som bäst uppfyller dina behov genom att samarbeta med din implementeringspartner och Microsoft för att ta reda på vilken månadstransaktionsstorlek du behöver.

SKU på ingångsnivå kallas *Basic*, och den mer högpresterande kallas *Standard*. Varje SKU förinlästes med ett visst antal månadstransaktioner. Du kan emellertid öka den månatliga transaktionsbudgeten genom att lägga till tilläggsprogram för överförbrukning för respektive SKU.

:::image type="content" source="media/SKUs-highlevel.png" alt-text="Tillägg för molnskalningsenheter.":::

> [!NOTE]
> Skalningsenhetstillägg kopplas inte till ett begränsat antal användare. De är tillgängliga för alla användare i ditt befintliga abonnemang (förutsatt att din administratör har tilldelat de användarroller som krävs för dem).

Inköpet av tilläggsprogrammet för skalningsenhet ger dig inte bara en månatlig volym av transaktioner utan ger dig även rätt till ett specifikt antal miljöplatser i LCS. För varje tilläggsprogram för molnbaserade skalningsenheter har du rätt till en ny produktionsplats och en ny sandbox-plats. Under registrerings läggs ett nytt LCS-projekt till med dessa platser. Användarrättigheterna för platserna binds, varför platserna måste användas som skalningsenheter med ett molnbaserat nav.

Tilläggsprogram för överförbrukning ger dig inte rätt till nya miljöplatser.

Om du vill skaffa fler sandbox-miljöer kan du köpa in ytterligare vanliga sandbox-platser. Microsoft kan sedan hjälpa dig att aktivera dessa platser som sandbox-skalningsenheter för hybridtopologin.


När du har planerat hur du ska registrera dig för den distribuerade hybridtopologin för Supply Chain Management använder du [portalen för skalningsansvarig](https://aka.ms/SCMSUM) för att påbörja registreringsprocessen. I portalen väljer du fliken **Dynamics 365-klientorganisationer**. Denna flik anger en lista över de klientorganisationer som ingår i ditt konto och där du är ägare eller miljöadministratör för en LCS-produkt.

Om innehavaren som du söker efter inte finns med i listan går du till [LCS](https://lcs.dynamics.com/v2) och kontrollerar att du är antingen miljöadministratör eller projektägare till LCS-projektet för den klientorganisationen. Endast Azure Active Directory (Azure AD)-konton från den valda klientorganisationen har behörighet att registrera sig.

> [!NOTE]
> När du har tillämpat ändringarna på LCS kan det ta upp till 30 minuter innan listan över klientorganisationerna avspeglar ändringarna.

Listan anger registreringsstatus för respektive klientorganisation.

:::image type="content" source="media/cloud_edge-EnableHybrid1.png" alt-text="Lista över klientorganisationer i fliken för Dynamics 365-klientorganisationer.":::

Välj **Klicka här för att komma igång** för att begära registrering för LCS-klientorganisationen. Du måste acceptera villkoren. Du måste också ange en e-postadress till företaget där Microsoft kan skicka meddelanden som är relaterade till registreringsprocessen.

:::image type="content" source="media/cloud_edge-EnableHybrid2.png" alt-text="Skicka registrering för en klientorganisation.":::

Microsoft kommer att granska din begäran och informera dig om nästa steg genom att skicka ett e-postmeddelande till den adress som du har angett i registreringsformuläret. Microsoft kommer att samarbeta nära dig för att möjliggöra skalningsenheter i hybridtopologin för ditt affärsscenario.

När registreringen är slutförd kan du använda porten för att konfigurera skalningsenheter och arbetsbelastningar.

### <a name="manage-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Hantera skalningsenheter och arbetsbelastningar med hjälp av portalen för skalningsenhetsansvarig

Gå till [portalen för skalningsenhetsansvarig](https://aka.ms/SCMSUM) och logga in med ditt klientkonto. På sidan **Konfigurera skalningsenheter** kan du lägga till en navmiljö om den inte redan finns med i listan. Du kan sedan välja det nav som du vill konfigurera med enheter och arbetsbelastningar.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Portal för skalningsenhetsansvarig, sidan Konfigurera skalningsenheter.":::

Om du vill lägga till en eller flera skalningsenheter som är tillgängliga i dina prenumerationer väljer du **Lägg till skalningsenheter**.

På fliken **Definierade arbetsbelastningar** använder du knappen **Skapa arbetsbelastning** för att lägga till en arbetsbelastning för lagerstyrning i en av dina skalningsenheter. För varje arbetsbelastning måste du ange kontexten för de processer som ska ägas av arbetsbelastningen. För distributionslagerstyrning arbetsbelastningar är sammanhanget ett specifikt lagerställe på en specifik webbplats och juridisk person.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Definiera dialogrutan för arbetsbelastning.":::

#### <a name="manage-workloads"></a><a name="manage-workloads"></a>Hantera arbetsbelastningar

När en eller flera arbetsbelastningar har aktiverats kan du använda alternativet **Hantera arbetsbelastningar** för att initiera och hantera processer, till exempel processer som beskrivs i följande tabell.

| Process | Beskrivning |
|---|---|
| Pausa skalningsenhetskommunikation | Pausa pipelinemeddelanden mellan hubb och skalningsenhet. Den process stoppar kommunikationen och tömmer dataförloppet mellan hubb och skaningsenheter. Du måste köra den här processen innan du kör en serviceoperation i Supply Chain Management på antingen hubben eller skaningsenheten, men du kan även använda den i andra situationer. |
| Återuppta skalningsenhetskommunikation | Återuppta pipelinemeddelanden mellan hubb och skalningsenhet. Du kanske måste använda den här processen efter att du har kört en serviceoperation i Supply Chain Management på antingen hubb eller skalningsenhet. |
| Uppgradera arbetsbelastningar | Synkronisera nya funktioner mellan arbetsbelastningar för hubb och skalningsenheter. Du kanske måste använda den här processen till exempel när servicen har medfört att datautbytesfrågorna har ändrats och/eller har lagt till nya register eller fält i arbetsbelastningen. |
| Överföra arbetsbelastningar till en skalningsenhet | Planera en arbetsbelastning som i nuläget körs på den hubb som ska flyttas till en skalningsenhet. När denna process körs flödar synkroniseringen av data, och både hubben och saklningsenheten ställs in för att ändra ägarskapet för arbetsbelastningen. |
| Överföra skalningsenhet till hubben | Planera en arbetsbelastning som i nuläget körs på en skalningsenhet som ska flyttas till hubben. När denna process körs flödar synkroniseringen av data, och både hubben och saklningsenheten ställs in för att ändra ägarskapet för arbetsbelastningen.
| Nödövergång till hubb | <p>Överför omedelbart en befintlig arbetsbelastning till hubben. *Denna process ändrar ägarskapet för enbart de data som för tillfället finns tillgängliga i hubben.*</p><p><strong>Varning:</strong> Denna process kan orsaka dataförlust vid icke-synkroniserade data och affärsbearbetningsfel. Därför ska den bara användas vid nödsituationer där affärsprocesser måste bearbetas i hubben eftersom skalningsenheten har ett avbrott som inte kan åtgärdas inom rimlig tid.</p> |
| Distribuerad avvecklingstopologi | Ta bort en distribuering för skalningsenhet och kör bara på hubben, utan bearbetning av arbetsbelastningen. |

:::image type="content" source="media/sum-manage-workloads.png" alt-text="Skalningsenhet och arbetsbelastningshantering.":::

> [!TIP]
> Med tiden läggs stegvisa förbättringar till i upplevelsen för skalningsenhetsansvarig i syfte att förenkla hanteringen av livscykler. De specifika möjligheterna för den aktuella versionen dokumenteras i en registreringshandbok som är tillgänglig för kunder som håller på att registrera sig för den distribuerade hybridtopologin för Supply Chain Management. <!-- KFM: Add a link to the handbook when it is published -->

## <a name="feature-management-considerations-for-workloads"></a>Hänsyn för funktionshantering för arbetsbelastningar

Det här avsnittet innehåller information om några viktiga aspekter som du bör ta hänsyn till när du installerar arbetsbelastningar, lägger till funktioner eller tar bort funktioner i en distribuerad topologidistribution. Flera scenarier kan påverka om du måste köra en [arbetslastuppgradering](#manage-workloads) när du har gjort ändringar. Det måste du dock vanligtvis göra när du uppdaterar eller lägger till nya datautbytesfrågor och/eller när du lägger till nya register eller fält i en tidigare installerad arbetsbelastning.

### <a name="mandatory-features-for-installing-a-workload"></a>Obligatoriska funktioner för installation av arbetsbelastning

När du installerar en arbetsbelastning skapar installationsprocessen en arbetsbelastningsdefinition som innehåller information om de dataregister som används när data synkroniseras mellan de två distributionerna. Skapandet av en arbetsbelastningsdefinition hanteras automatiskt baserat på funktionerna som för närvarande är aktiverade i [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). I följande tabell beskrivs de funktioner som måste vara aktiverade för att arbetsbelastningsdefinitionerna som krävs för att köra ett lagerställe eller en tillverkningsarbetsbelastning ska kunna köras.

| Obligatorisk funktion | Arbetsbelastning |
|---|---|
| Automatisk tilldelning av GUID när användaren skapar något i WHS | Lagerställe |
| Arbetsspärr för hela organisationen | Lagerställe |
| Information om etikett för leveranspåfyllnad | Lagerställe |
| Stöd för skalningsenhet för arbetslistor för distributionslagerapp | Lagerställe |
| Produktionsgolvskörning | Tillverkning |

När du distribuerar en arbetsbelastning genom att använda [användningsverktygen för skalningsenhet för one-box-utvecklingsmiljöer](https://github.com/microsoft/SCMScaleUnitDevTools) eller [portalen för skalningsenhetsansvarig](https://sum.dynamics.com), aktiveras alla obligatoriska funktioner automatiskt. Om du däremot gör en manuell testdistribution som saknar en eller flera obligatoriska funktioner misslyckas arbetsbelastningsinstallationen och du får ett meddelande med de funktioner som saknas. Du måste sedan aktivera dessa funktioner manuellt och starta om arbetsbelastningsinstallationen.

### <a name="enabling-or-disabling-features-that-have-data-synchronization-dependencies"></a>Aktivera eller inaktivera funktioner som har datasynkroniseringsberoenden

Funktioner som påverkar valet av data som synkroniseras mellan hubben och dess skalenheter påverkar också hur arbetsbelastningsdefinitionen skapas. Därför är det viktigt att de här funktionerna aktiveras innan du installerar arbetsbelastningen. Om du aktiverar den här typen av funktion medan du kör en arbetsbelastning måste du återskapa arbetsbelastningsdefinitionen genom att köra en [arbetslastuppgradering](#manage-workloads) när du har aktivera funktionen. På samma sätt, om du inaktiverar en funktion som har datasynkroniseringsberoende medan du kör en arbetsbelastning, måste du köra en[arbetslastdefinitionen](#manage-workloads) för att ta bort relevant datasynkroniseringsinformation från arbetslastdefinitionen.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
