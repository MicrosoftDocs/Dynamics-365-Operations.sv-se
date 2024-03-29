---
title: Felsöka problem från uppgraderingar av appar för ekonomi och drift
description: Den här artikeln innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som är relaterade till uppgradering av appar för ekonomi och drift.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 7ab75c3a7b6c53982a32658f376a9fd148c023e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289557"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>Felsöka problem från uppgraderingar av appar för ekonomi och drift

[!include [banner](../../includes/banner.md)]





Den här artikeln innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan appar för ekonomi och drift och Dataverse. I synnerhet ger den information som kan hjälpa dig att åtgärda problem som är relaterade till uppgradering av appar för ekonomi och drift.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="database-synchronization-errors"></a>Databassynkroniseringsfel

**Den roll som krävs för att åtgärda problemet:** systemadministratör

Du kan komma att få ett felmeddelande som liknar följande exempel när du försöker använda tabellen **DualWriteProjectConfiguration** för att uppdatera en app för ekonomi och drift till plattformsuppdatering 30.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Gör så här om du vill åtgärda problemet.

1. Logga in på den virtuella datorn (VM) för appen för ekonomi och drift.
2. Öppna Visual Studio som administratör och öppna programobjektträd (AOT).
3. Sök efter **DualWriteProjectConfiguration**.
4. I programobjektträdet högerklickar du på **DualWriteProjectConfiguration** och väljer **Lägg till i nytt projekt**. Välj **OK** om du vill skapa det nya projekt som använder standardalternativ.
5. I Solution Explorer, högerklicka på **projektegenskaper** och ställ in **Synkronisera databas i version** till **Sant**.
6. Skapa projektet och bekräfta att versionen lyckades.
7. I menyn **Dynamics 365** väljer du **Synkronisera databas**.
8. Välj **synkronisera** om du vill utföra en fullständig databassynkronisering.
9. När den fullständiga databassynkroniseringen lyckas kör du steget för databassynkronisering i Microsoft Dynamics Lifecycle Services (LCS) och använder de manuella uppgraderingsskripten så att du kan fortsätta med uppdateringen.

## <a name="missing-table-columns-issue-on-maps"></a>Problem med kolumner i saknade register på mappningar

**Den roll som krävs för att åtgärda problemet:** systemadministratör

På sidan **dubbelriktad skrivning** kan du få ett felmeddelande som liknar följande exempel:

*Källfält fältnamn \<field name\> saknas i schemat*

![Exempel på felmeddelandet för "källkolumn saknas".](media/error_missing_field.png)

Lös problemet genom att först följa de här stegen för att kontrollera att kolumnerna finns i tabellen.

1. Logga in på den virtuella datorn för appen för ekonomi och drift.
2. Gå till **Arbetsytor \> Datahantering**, välj panelen **Ramverksparametrar** och sedan på fliken **Tabellinställningar** välj **Uppdatera tabellistan** för att uppdatera tabellerna.
3. Gå till **Arbetsytor \> Datahantering**, välj fliken **Datatabeller** och kontrollera att tabellen finns med i listan. Om tabellen inte finns med loggar du in på den virtuella datorn för appen för ekonomi och drift och ser till att tabellen är tillgänglig.
4. Öppna sidan **Tabellmappning** från sidan **Dubbelriktad skrivning** i appen för ekonomi och drift.
5. Markera **Uppdatera tabellista** om du vill fylla i kolumnerna i tabellmappningarna automatiskt.

Om problemet fortfarande inte är åtgärdat följer du stegen nedan.

> [!IMPORTANT]
> De här stegen vägleder dig genom processen att ta bort en tabell och sedan lägga till den igen. Se till att du följer stegen exakt om du vill undvika problem.

1. I appen för ekonomi och drift går du till **Arbetsytor \> Datahantering** och väljer panelen **Datatabeller**.
2. Sök efter den tabell som saknar attributet. Klicka på **Ändra målmappning** i verktygsfältet.
3. I fönstret **Mappa mellanlagring till mål**, klicka på **Generera källmappning**.
4. Öppna sidan **Tabellmappning** från sidan **Dubbelriktad skrivning** i appen för ekonomi och drift.
5. Om attributet inte fylls i automatiskt på mappningen lägger du till det manuellt genom att klicka på knappen **Lägg till attribut** och sedan på **Spara**. 
6. Markera mappningen och klicka på **Kör**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
