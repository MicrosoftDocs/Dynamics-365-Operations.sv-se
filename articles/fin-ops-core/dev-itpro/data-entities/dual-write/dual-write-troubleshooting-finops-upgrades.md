---
title: Felsöka problem som rör uppgraderingar av Finance and Operations-appar
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som är relaterade till uppgradering av Finance and Operations-appar.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 07d6bd0bab796d7839daa2bad91f7e88c2e881b5
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997928"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a>Felsöka problem som rör uppgraderingar av Finance and Operations-appar

[!include [banner](../../includes/banner.md)]



Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service. Särskilt ger de information som kan hjälpa dig att åtgärda problem som är relaterade till uppgradering av Finance and Operations-appar.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="database-synchronization-errors"></a>Databassynkroniseringsfel

**Den roll som krävs för att åtgärda problemet:** systemadministratör

Ett felmeddelande av följande slag kan visas när du försöker använda entiteten **DualWriteProjectConfiguration** för att uppdatera en Finance and Operations-app till plattformsuppdatering 30.

```console
Infolog diagnostic message: 'Cannot select a record in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Gör så här om du vill åtgärda problemet.

1. Logga in på den virtuella datorn (VM) för Finance and Operations-appen.
2. Öppna Visual Studio som administratör och öppna programobjektträd (AOT).
3. Sök efter **DualWriteProjectConfiguration**.
4. I programobjektträdet högerklickar du på **DualWriteProjectConfiguration** och väljer **Lägg till i nytt projekt**. Välj **OK** om du vill skapa det nya projekt som använder standardalternativ.
5. I Solution Explorer, högerklicka på **projektegenskaper** och ställ in **Synkronisera databas i version** till **Sant**.
6. Skapa projektet och bekräfta att versionen lyckades.
7. I menyn **Dynamics 365** väljer du **Synkronisera databas**.
8. Välj **synkronisera** om du vill utföra en fullständig databassynkronisering.
9. När den fullständiga databassynkroniseringen lyckas kör du steget för databassynkronisering i Microsoft Dynamics Lifecycle Services (LCS) och använder de manuella uppgraderingsskripten så att du kan fortsätta med uppdateringen.

## <a name="missing-entity-fields-issue-on-maps"></a>Entitetsfält som saknas problem i kartor

**Den roll som krävs för att åtgärda problemet:** systemadministratör

På sidan **dubbelriktad skrivning** kan du få ett felmeddelande som liknar följande exempel:

*Källfält fältnamn \<field name\> saknas i schemat*

![Exempel på felmeddelandet för källfält saknas](media/error_missing_field.png)

Lös problemet genom att först följa de här stegen för att kontrollera att fälten finns i entiteten.

1. Logga in på den virtuella datorn för Finance and Operations-appen.
2. Gå till **Arbetsytor \> Datahantering** , välj panelen **Rramverksparametrar** och sedan på fliken **Entitetsinställningar** välj **Uppdatera entitetslistan** för att uppdatera enheterna.
3. Gå till **Arbetsytor \> Datahantering** , välj fliken **Dataentiteter** och kontrollera att entiteten finns med i listan. Om entiteten inte finns med loggar du in på den virtuella datorn för Finance and Operations-appen och ser till att enheten är tillgänglig.
4. Öppna sidan **entitetsmappning** från sidan **dubbelriktad skrivning** i Finance and Operations-appen.
5. Markera **uppdatera entitetslista** om du vill fylla i fälten i entitetsmappningarna automatiskt.

Om problemet fortfarande inte är åtgärdat följer du stegen nedan.

> [!IMPORTANT]
> De här stegen vägleder dig genom processen att ta bort en enhet och sedan lägga till den igen. Se till att du följer stegen exakt om du vill undvika problem.

1. I Finance and Operations-appen, gå till **Arbetsytor \> Datahantering** och välj panelen **Dataentiteter**.
2. Sök efter den entitet som saknar attributet. Klicka på **Ändra målmappning** i verktygsfältet.
3. I fönstret **Mappa mellanlagring till mål** , klicka på **Generera källmappning**.
4. Öppna sidan **entitetsmappning** från sidan **dubbelriktad skrivning** i Finance and Operations-appen.
5. Om attributet inte fylls i automatiskt på kartan lägger du till det manuellt genom att klicka på knappen **Lägg till attribut** och sedan på **Spara**. 
6. Markera mappningen och klicka på **Kör**.
