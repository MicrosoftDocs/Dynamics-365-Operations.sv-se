---
title: Utöka Talent genom att använda PowerApps och Microsoft Flow- exempelscenarier
description: Det här ämnet beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 for Talent som använder Microsoft PowerApps och Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c113b0f4ab2c8e44d00fcfca3f0a6ca828a854ae
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519100"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a>Utöka Talent genom att använda PowerApps och Microsoft Flow- exempelscenarier

Det här ämnet beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 for Talent som använder Microsoft PowerApps och Microsoft Flow. Du kan importera lösningspaketet som associeras med varje exempel i din PowerApps-miljö. Du kan sedan använda paketen antingen som vägledning eller som utgångspunkt för att implementera scenarier som gäller för din organisation.

> [!IMPORTANT]
> Om du vill använda de mallar och program som beskrivs i det här avsnittet ”i befintligt skick” bör du testa dem och se till att de täcker alla de scenarier som avser implementeringen.


## <a name="prerequisites"></a>Förutsättningar

- Om du vill importera paket måste användarna ha behörighet **Environment Maker**.
- Användare måste ha en PowerApps Plan 2-licens eller en PowerApps Plan 2 utvärderingslicens för att exportera eller importera appar.

## <a name="flow--form-connect"></a>Flöde – formuläret Ansluta

Mallen **flöde – formuläret Ansluta** kan användas för att läsa data från Microsoft Forms och lagra det i en Common Data Service-enhet.

Den här mallen kan utökas så att den kan användas för andra scenarier. Nedan följer några exempel:

- Hämta kandidatens bedömningar.
- Hämta resultaten från kursens enkäter.
- Kompilera ett bibliotek med intervjufrågor för personaladministratörer (HR).
- Hämta kandidatens utvärdering av intervjuprocessen

I Microsoft Dynamics 365: Attract, kan formulär visas i kandidatportalen och kandidater kan fylla i information. Formulär kan också vara inbäddade som aktiviteter i en jobbmall.

När en kandidat skickar ett formulär, hämtar Microsoft Flow formuläröverföringen, läser in data och lagrar den Common Data Service-enhet.

För att hämta mallen **flöde – formuläret Ansluta** och anpassad entitetsstruktur, gå till [flöde – formuläret Ansluta](https://go.microsoft.com/fwlink/?linkid=2081988) på Microsoft Download Center.

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a>Initiera och hämta parametrar som skickades till Powerapps

Mallen **starta och hämta parametrar som skickades till Powerapps** kan användas som utgångspunkt för vissa PowerApps-situationer som är specifika för Attract. Den innehåller alla standardparametrar som skickas av Attract, t.ex. **Jobbansökan**, **kandidat-ID**, och **JobID**.

Den här mallen kan användas för att hämta kandidatens bedömningsformulär, så att en anställande chef kan visa den bedömning som en kandidat har fyllt i.

Appar som har skapats med hjälp av PowerApps kan vara inbäddade i jobbmallen i Attract.

För att hämta mallen **initiera och hämta parametrar som skickades till Powerapps** och anpassad entitetsstruktur, gå till [starta och hämta parametrar som skickades till Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) på Microsoft Download Center.

## <a name="integration-with-office-365"></a>Integration med Office 365

Appen **Integrering med Office 365** kan användas för att hämta teaminformation för inloggade användare från Microsoft Office 365. Den refererar till arbetare i Talent för att hämta instämplings- och utstämplingsinformation och undantagsregistreringar. Instämplings- och utstämplingsinformation lagras i anpassade Common Data Service-enheter. Förutsättningen är att rubrikerna fylls i från tredjepartssystem via integrering.

Den här appen kan utökas så att den kan användas för andra scenarier. Exempelvis användas den för att visa semesterinformation för team, kalenderhändelser och alla teamspecifika händelser.

För att hämta appen **integrering med Office 365** och anpassad entitetsstruktur, gå till [Integrering med Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) på Microsoft Download Center.

## <a name="flow--email-notification"></a>Föde - E-postmeddelande

Mallen **Flöde – e-postmeddelanden** kan användas för e-postmeddelandescenarier. Den kan användas för att utlösa e-postmeddelanden till kandidater som anställningsteamet avvisar under någon fas i rekryteringsprocessen.

Den här mallen kan utökas för att spåra ändringar i kandidatfasen genom hela rekryteringsprocessen och skicka meddelanden till anställningsteamet och kandidaterna.

I allmänhet kan flöden för entiteter som är lagrade i Common Data Service ställas in för att skicka meddelanden om händelser som inträffar i Core HR, Attract eller Dynamics 365 Talent: Onboard.

För att hämta mallen **Flöde – e-postmeddelanden**, gå till [Flöde – e-postmeddelanden](https://go.microsoft.com/fwlink/?linkid=2082103) på Microsoft Download Center.

## <a name="flow--sql-connect-and-execute"></a>Flöde – anslut och kör SQL

Mallen **Flöde – anslut och kör SQL** ansluter till Microsoft SQL Server och gör att SQL-frågor kan köras.

Även om den här mallen har utformats för att läsa och uppdatera SQL-register kan den utökas så att den kan användas för andra scenarier. Den kan exempelvis användas för att fylla på ett mellanlagringsregister i Common Data Service med poster från SQL Server och regelbundet synkronisera mellanlagringsregister med hjälp av en stegvis distribution från SQL Server.

För att hämta mallen **flöde – ansluta och köra SQL**, gå till [flöde – ansluta och köra SQL](https://go.microsoft.com/fwlink/?linkid=2081789) på Microsoft Download Center.

## <a name="flow--sharepoint-integration"></a>Flöde SharePoint-integrering

Mallen **Flöde – SharePoint integrering** kan användas för att läsa in data från en Microsoft SharePoint-lista, jämföra listan med fältvärden för någon Common Data Service entitet och skicka resultatet av jämförelsen som ett e-postmeddelande. 

En organisation kan ha en uppsättning med kunskaper som den kräver snarast. Dessa kunskaper kan lagras i SharePoint som en SharePoint lista. Då en kandidat ansöker om ett jobb som en uppsättning kunskaper anges för, om det finns en betydande matchning mellan kandidatens kunskaper och de kunskaper som är lagrade i SharePoint skickas ett e-postmeddelande. På så sätt fylls befattningar som krävs snarast snabbare eftersom meddelanden hjälper rekryterare att kontakta och anställa kandidater i hela organisationen.

Den här mallen kan utökas så att den kan användas för vissa situationer som omfattar SharePoint-integration.

För att hämta mallen **Flöde – SharePoint Integration**, gå till [Flöde – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) på Microsoft Download Center.

## <a name="admin-console-to-manage-talent-pools"></a>Administrationskonsol för hantering av talangpooler

När du aktiverar integrering med LinkedIn skapar Attract automatiskt en LinkedIn-talangpool automatiskt. När en rekryterare utbyter InMail med en rekrytering via LinkedIn skapar Attract en profil för rekryteringen och rekryteringen blir medlem i den LinkedIn talangpoolen. Denna PowerApps-app är användbar för att ordna om kandidater i talangpooler utifrån färdighet.

Kör den här PowerApps-appen som en administrationskonsol när du vill utföra följande uppgifter:

- Lista kandidater i en talangpool
- Lägg till och ta bort kandidater från en talangpool
- Flytta kandidater från en talangpool till en annan
- Ta reda på om kandidater redan ingår i en talangpool innan du flyttar dem
- Kontrollera kompetenserna hos kandidater innan du flyttar dem till andra talangpooler

Det här PowerApps-appen använder många-till-många-relationer, så du kan använda den som en mall för andra scenarier där du behöver extrahera poster som har många-till-många-relationer.

Om du vill hämta **Administrationskonsol för hantering av talangpooler**, gå till [Administrationskonsol för hantering av talangpooler](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) på Microsoft Download Center.

## <a name="additional-resources"></a>Ytterligare resurser

[Appen Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[Migrera mellan innehavare och program](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)
