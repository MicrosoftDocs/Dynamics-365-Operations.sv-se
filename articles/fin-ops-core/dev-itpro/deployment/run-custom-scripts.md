---
title: Köra anpassade X++-skript utan avbrott
description: I den här artikeln beskrivs hur du överför och kör de paket som kan distribueras och som innehåller anpassade X++-skript utan att behöva pausa systemet.
author: AndersGirke
ms.date: 12/16/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-12-16
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 3d00f842da69f889738fbcb293c7489bb018e810
ms.sourcegitcommit: f62c9b24c2205d03e2fd6e7c67f7b5c316233b12
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2022
ms.locfileid: "9598093"
---
# <a name="run-custom-x-scripts-with-zero-downtime"></a>Köra anpassade X++-skript utan avbrott

[!include [banner](../includes/banner.md)]

Med den här funktionen kan du överföra och köra distributionsbara paket som innehåller anpassade X++-skript utan att behöva gå igenom Microsoft Dynamics Lifecycle Services (LCS) eller pausa ditt system. Det gör att du kan korrigera mindre inkonsekvenser i data utan att orsaka störande driftstopp.

Fördelen med att använda ett X++-skript för att korrigera mindre inkonsekvenser av data är att systemet automatiskt justerar alla relaterade register när skriptet körs. Det här minimerar risken för inkonsekvenser och minskar risken för inkonsekvenser.

> [!IMPORTANT]
> Den här funktionen är endast avsedd för korrigering av mindre inkonsekvenser i data. Den får inte användas i följande syften eller något annat syfte:
>
> - Datainsamling
> - Schemaändringar
> - Datamigrering eller andra processer som körs på längre sikt
> - Korrigering av data som kan korrigeras på andra sätt, till exempel vanliga affärsprocesser, datakonsekvensverktyg eller andra självbetjäningsverktyg
>
> Med funktionen kan behöriga användare ändra enheter och deras poster direkt, utan att behöva köra den affärslogik som är kopplad till dessa enheter. Dessa ändringar kan medföra problem med dataintegriteten. Därför kan din organisation kräva att du får godkännande och signering från interna och externa revisorer (eller andra motsvarande motsvarande uppsägningar) innan och/eller efter att du kör ett skript. Av efterföljandeskäl kanske ändringar som påverkar vissa egenskaper också måste lämnas ut i externa rapporter (till exempel bokslut) eller rapporteras till myndighet. Din organisation är ansvarig för alla ändringar som görs av dess data via den här funktionen, godkännande och godkännande och spridning av ändringarna samt efterföljande av tillämpliga lagar. Du bär alla risker med att använda den här funktionen.

Alla distributionsbara paket som överförs till systemet går genom ett obligatoriskt arbetsflöde. Som en säkerhetsåtgärd, och för att säkerställa uppdelningen av arbetsuppgifterna, kan användaren som överför ett paket som kan distribueras inte godkänna det för nästa steg i arbetsflödet. En annan användare måste godkänna den. När paketet har godkänts kan dock användaren som förde över det utföra resten av stegen.

Systemet kräver att alla paket som kan distribueras går igenom en testkörning. Innan skriptet ska tillåtas köras på produktionsdata måste en användare validera att resultatet är korrekt genom att välja **Godta testlogg**. Om utdata inte är korrekt måste användaren markera paketet som misslyckat genom att välja **Avbryt**. I det här fallet tillåts inte skriptet att köras på produktionsdata.

Varje överfört paket sparas i systemet och går igenom ett definierat arbetsflöde med händelser. För varje händelse behåller systemet en logg som innehåller en tidstämpel och identiteten för den person som utförde händelsen. På det här sättet säkerställer systemet att det finns en redovisningskedja.

Som illustrationen nedan visar visar systemet information om hur varje paket som kan distribueras körs i X++ och vilka enheter som utser.

![Sidan Skriptdetaljer.](media/script-details.png "Sidan Skriptdetaljer")

## <a name="assign-duties-to-users-to-control-access"></a>Tilldela arbetsuppgifter till användarna för att kontrollera åtkomsten

Denna funktion har följande uppgifter. Administratörer kan använda dessa arbetsuppgifter för att kontrollera åtkomsten till funktionen.

- **Underhåll anpassade skript** – Denna uppgift ger möjlighet att överföra, testa, verifiera och köra anpassade X++-skript i miljöer (testning av användargodkännande \[UAT\] och produktion).
- **Godkänn anpassade skript** – Denna uppgift ger möjlighet att godkänna ett överfört anpassat X++-skript. Godkännandet är ett obligatoriskt steg innan ett skript kan testas, verifieras och köras.

För att minimera risken för skadlig åtgärd måste varje skript explicit godkännas av en annan användare än den användare som överförde det. Innan du kan använda den här funktionen i organisationen måste en administratör tilldela de föregående uppgifterna till minst två relevanta och mycket betrodda användare. Även om en enskild användare kan ha båda arbetsuppgifterna kommer den användaren inte att kunna godkänna sina egna skript.

## <a name="create-a-deployable-package"></a>Skapa ett driftfärdigt paket

Funktionen kräver ett vanligt distribuerat paket som kan skapas i Visual Studio. Mer information finns i [skapa distribuerbara paket av modeller](../deployment/create-apply-deployable-package.md).

Ditt paket som kan distribueras måste innehålla exakt en körbar X++-klass. Det måste alltså ha en klass som innehåller en metod som har följande signatur.

```xpp
public static void main(Args _args)
```

> [!NOTE]
> Namnet på huvudmetoden måste vara gemener.

## <a name="code-example"></a>Kodexempel

Följande kodexempel visar hur ett paket som kan distribueras kan struktureras.

```xpp
class MyScriptClassForIssueXYZ
{
    public static void main(Args _args)
    {
        if (curExt() != 'DAT')
        {
            throw error("This script must run in the DAT company!");
        }

        ttsbegin;

        MyTable myTable;

        update_recordset myTable
            setting myField = 17
            where myTable.myReference == 'xyz';

        if (myTable.RowCount() != 1)
        {
            throw error("Not updating the expected row!");
        }

        info("Success");
  
        ttscommit;
    }

}
```

## <a name="best-practices"></a>Regelverk

I listan nedan beskrivs några exempel på hur du kan skriva, implementera och köra ett skript. Listan är inte fullständig och bör endast betraktas som riktlinjer.

- **Skriv** ett meddelande vid slutfört i slutet av skriptet. På det här sättet kan du se att skriptet kördes utan undantag.
- **Lägg till** en explicit hantering av transaktionssområdet.
- **Använd** befintlig affärslogik, t.ex. `update()` metoder, men **gå inte förbi** genom att använda business `doUpdate()`, `doInsert()` och `doDelete()` metoder. Det här sättet hjälper dig att se till att beroende data hanteras korrekt. Det minskar också risken för ytterligare data inkonsekvenser.
- **Försäkra** företagssammanhanget. Det här arbetssättet visar vanliga misstag när ett skript körs. Det visar till exempel om skriptet körs i fel företag.
- **Försäkra** att antalet påverkade poster matchar dina önskemål. Det här sättet visar om data oväntat skiftades i systemet medan skriptet förbereddes.
- **Använd** unika klassnamn för varje skript (till exempel genom att inkludera en referens till en arbetspost i namnet). Denna metod förhindrar namnproblem när du överför skriptet. Om ett skript måste skrivas på nytt måste du ge det ett nytt namn.
- **Testa** först varje skript i en miljö som inte är av tillverkningsmiljö. Testa för avsedd effekt och för oavsiktliga sidoeffekter på relaterade data. Se till att alla affärsprocesser som kan påverkas kan slutföras och slutföras helt efteråt.

## <a name="upload-and-run-a-deployable-package"></a>Överföra och köra ett paket som kan distribueras

Använd följande procedur för att ladda upp och köra ett skript.

1. I ditt appar för ekonomi och drift går du till **Systemadministration \> Periodiska uppgifter \> Databas \> Anpassade skript**.
1. Välj **överför**.
1. Välj det paket som kan distribueras och som du skapat på det sätt som beskrivs tidigare i den här artikeln. Du uppmanas att ange syftet med skriptet.
1. Skriptet måste nu godkännas av en annan användare än den som förde över det. Godkännaren måste följa dessa steg:

    1. Gå till **Systemadministration \> periodisk \> databas \> anpassade skript**.
    1. Välj det skript som ska godkännas och välj sedan **Detaljer**.
    1. I Åtgärdsfönstret, på fliken **Processarbetsflöde** i gruppen **Starta**, välj **Godkänn** eller **Avvisa**. Om du väljer **Godkänn** markeras skriptet som godkänt och låses upp för testning. Om du väljer **Avvisa** är skriptet låst. I båda fall loggas händelsen och en kopia av skriptet sparas i systemet.

1. Skriptet måste testas för att säkerställa att det gör vad det ska göra. Testaren kan vara samma som överföraren eller godkännaren, eller så kan det vara en tredje användare som har den behörighet som krävs. Testaren måste följa dessa steg:

    1. Gå till **Systemadministration \> periodisk \> databas \> anpassade skript**.
    1. Välj det skript som ska testas och välj sedan **Detaljer**.
    1. I Åtgärdsfönstret, på fliken **Processarbetsflöde**, i gruppen **Testa**, markerar du **Kör test**. Skriptet körs i en tillfällig transaktion som avbryts automatiskt i systemet medan diverse loggar och SQL-satser samlas in.
    1. När skriptet har körts kan du granska loggarna och verifiera att resultatet uppfyller dina önskemål. Gör något av följande:

        - Om du är nöjd med testresultatet väljer du **Godkänn testlogg** i gruppen **Test** på fliken **Bearbeta arbetsflöde** i åtgärdsfönstret för att köra skriptet. Händelseloggen visar det fakta som skriptet har testats för, och vem som har testat det och när.
        - Om du inte är nöjd med testresultatet väljer du **Avbryt** i gruppen **Slut** på fliken **Bearbeta arbetsflöde** i åtgärdsfönstret för att köra skriptet. Systemet behåller en kopia av skriptet tillsammans med en logg över dess historik.

1. När du är säker på att skriptet uppfyller dina önskemål väljer du **Kör** i gruppen **Kör** på fliken **Processarbetsflöde** i åtgärdsfönstret för att köra det. Det här kommandot gör samma sak som den föregående testkörningen, men transaktionen kommer att utföras i slutet.
1. När skriptet har körts kontrollerar du resultatet och bekräftar att skriptet har arbetat som det ska. Gör något av följande:

    - Om du är nöjd med resultatet väljer du **Syftet är löst** i gruppen **Slut** på fliken **Processarbetsflöde** i åtgärdsfönstret. Händelseloggen kommer att återspegla det faktum att skriptet kördes framgångsrikt, och det kommer att indikera vem som verifierat skriptet och när. Skriptet sparas, men är nu låst och kan inte köras igen.
    - Om du inte är nöjd med resultatet väljer du **Syftet är olöst** i gruppen **Slut** på fliken **Processarbetsflöde** i åtgärdsfönstret. Händelseloggen kommer att återspegla det faktum att skriptet inte uppfyllde sitt avsedda syfte, och den kommer att indikera vem som körde skriptet och när. Skriptet sparas, men är nu låst och kan inte köras igen. Systemet ångrar emellertid inte automatiskt skriptåtgärden. Du kanske måste skriva, importera och köra ett nytt skript för att ångra den effekt som det misslyckade skriptet hade på systemet.

Det som du väljer i det sista steget definierar den slutliga statusen för skriptet. Du kan upprepa processen efter behov.

## <a name="upload-and-run-a-deployable-package-through-lcs"></a>Överföra och köra ett paket som kan distribueras via LCS

I stället för att distribuera ditt distribuerade paket via användargränssnittet för ditt appar för ekonomi och drift kan du i enlighet med beskrivningen i föregående avsnitt överföra det till LCS och använda den vanliga proceduren för att distribuera det. För mer information, se [Installera distribuerbara paket från kommandoraden](../deployment/install-deployable-package.md).

Även om det här arbetssättet har färre begränsningar ger det mindre felsskydd. Eftersom det kräver en omstart av alla servrar orsakar det dessutom ett visst antal drifttid.

