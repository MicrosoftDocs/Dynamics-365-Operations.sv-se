---
title: Felsöka problem med direkt synkronisering
description: Den här artikeln innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem med direkt synkronisering.
author: RamaKrishnamoorthy
ms.date: 08/19/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 9d27331b940a95168810c2f1ec4ae240a9df93a8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896717"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Felsöka problem med direkt synkronisering

[!include [banner](../../includes/banner.md)]



Den här artikeln innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Ekonomi och Drift-appar och Microsoft Dataverse. Särskilt ger den information som kan hjälpa dig att åtgärda problem med direkt synkronisering.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. Varje avsnitt förklarar om en viss roll eller vissa autentiseringsuppgifter krävs.

## <a name="live-synchronization-shows-an-error-when-you-create-a-row"></a>Live-synkroniseringen visar ett fel när du skapar en rad

Följande felmeddelande kan visas när du skapar i en rad i en Ekonomi och Drift-app:

*\[{\\"fel\\":{\\"kod\\":\\"0x80072560\\",\\"meddelande\\":\\"Användaren är inte en medlem av organisationen.\\"}}\], Fjärrservern returnerade ett fel: (403) förbjudet."}}".*

Om du vill åtgärda problemet följer du stegen i [Systemkrav och förutsättningar](requirements-and-prerequisites.md). För att kunna utföra dessa steg måste användare av appen med dubbelriktad skrivning som skapades i Dataverse ha rollen systemadministratör. Teamet för standardägargrupp måste också ha rollen systemadministratör.

## <a name="live-synchronization-shows-an-error-when-you-try-to-save-table-data"></a>Live-synkroniseringen visar ett fel när du försöker spara tabelldata

**Den roll som krävs för att åtgärda problemet:** systemadministratör

Följande felmeddelande kan visas när du försöker spara tabelldata i en Ekonomi och Drift-app:

*Det går inte att spara ändringarna i databasen. Arbetsenheten kan inte genomföra transaktionen. Det gick inte att skriva data till entitets-uoms. Skrivningar till UnitOfMeasureEntity misslyckades med felmeddelandet Det gick inte att synkronisera med entitets-uoms.*

För att lösa problemet måste du se till att de förutsatta referensdata finns i både Ekonomi och Drift-appen och Dataverse. Till exempel om en kundpost tillhör en viss kundgrupp, se till att den kundgruppens post finns i Dataverse.

Om det finns data på båda ställena och du har bekräftat att problemet inte är datarelaterat följer du dessa steg.

1. Öppna entiteten **DualWriteProjectConfigurationEntity** genom att använda Excel-tillägget. För att använda tillägget, aktivera designläge i Ekonomi och Drift Excel-tillägget och lägg till **DualWriteProjectConfigurationEntity** till ett kalkylblad. Mer information finns i [Visa och uppdatera enhetsdata med Excel](../../office-integration/use-excel-add-in.md).
2. Välj och ta bort posterna som har problem i mappningen och projektet för dubbelriktad skrivning. Det kommer att finnas två poster för varje mappning för dubbelriktad skrivning.
3. Publicera ändringarna med hjälp av Excel-tillägget. Det här steget är viktigt eftersom det tar bort posterna från entiteten och de underliggande tabellerna.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Hantera läs- eller skrivbehörighetsfel när du skapar data i en Ekonomi och Drift-app

Felmeddelande Felaktig begäran kan visas när du skapar data i en Ekonomi och Drift-app.

![Exempel på felmeddelandet Felaktig begäran.](media/error_record_id_source.png)

För att åtgärda problemet måste du aktivera det saknade privilegiet genom att tilldela rätt säkerhetsroll till teamet för den mappade Dynamics 365 Sales- eller Dynamics 365 Customer Service-affärsenheten.

1. I Ekonomi och Drift-appen, leta reda på den affärsenhet som är mappad till anslutningsuppsättningen för dataintegrering.

    ![Organisationsmappning.](media/mapped_business_unit.png)

2. I Customer Engagement-appen loggar du in i miljön, går till **Inställningar \> Säkerhet** och letar rätt på teamet för den mappade affärsenheten.

    ![Team av den mappade affärsenheten.](media/setting_security_page.png)

3. Öppna sidan för teamet för redigering och välj sedan **Hantera roller**.

    ![Knappen Hantera roller.](media/manage_team_roles.png)

4. Tilldela rollen läs-/skrivbehörighet för de relevanta tabellerna i dialogrutan **Hantera teamroller** och välj **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>Åtgärda synkroniseringsproblem i en miljö som har en nyligen ändrad Dataverse-miljö

**Den roll som krävs för att åtgärda problemet:** systemadministratör

Följande felmeddelande kan visas när du skapar data i en Ekonomi och Drift-app:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Det gick inte att generera nyttolast för entiteten CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Skapande av nyttolast misslyckades med fel URI: URI är tom."}\],"isErrorCountUpdated":true}*

Så här ser felet ut i Customer Engagement-appen:

> Ett oväntat fel har inträffat från ISV-kod. (ErrorType = ClientError) Ett oväntat fel uppstod från ISV-koden. Oväntat undantag från plugin-programmet (kör): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: misslyckades att bearbeta ett entitetskonto – (Ett anslutningsförsök misslyckades eftersom den anslutna parten inte svarade ordentligt efter en tidsperiod, eller upprättad anslutning misslyckades eftersom ansluten värd inte har svarat.

Det här felet uppstår om Dataverse-miljön återställs felaktigt när du försöker skapa data i Ekonomi och Drift-appen.

> [!IMPORTANT]
> Om du har länkat om miljöerna måste du stoppa alla entitetsmappningar innan du fortsätter med de begränsande stegen.

Om du vill åtgärda problemet måste du utföra stegen både i Dataverse och Ekonomi och Drift-appen.

1. I Ekonomi och Drift-appen, följ dessa steg:

    1. Öppna entiteten **DualWriteProjectConfigurationEntity** genom att använda Excel-tillägget. För att använda tillägget, aktivera designläge i Ekonomi och Drift Excel-tillägget och lägg till **DualWriteProjectConfigurationEntity** till ett kalkylblad. Mer information finns i [Visa och uppdatera enhetsdata med Excel](../../office-integration/use-excel-add-in.md).
    2. Välj och ta bort posterna som har problem i mappningen och projektet för dubbelriktad skrivning. Det kommer att finnas två poster för varje mappning för dubbelriktad skrivning.
    3. Publicera ändringarna med hjälp av Excel-tillägget. Det här steget är viktigt eftersom det tar bort posterna från entiteten och de underliggande tabellerna.
    4. Bidra till att förhindra fel när du länkar om Ekonomi och Drift- eller Dataverse-miljön genom att se till att inga konfigurationer för dubbelriktad skrivning finns kvar.

2. Följ dessa steg i Dataverse:

    1. Logga in i din Dataverse-miljö (till exempel `https://*****.crm.dynamics.com/`).
    2. Gå till **Avancerade inställningar** \> **Avancerad sökning**.
    3. Välj **körningskonfiguration för DualWrite**.
    4. Välj kolumnen som du vill visa.
    5. Välj **Resultat** för att visa konfigurationerna.
    6. Ta bort alla instanser.

3. I Ekonomi och Drift-appen, följ dessa steg:

    1. Öppna entiteten **DualWriteProjectConfigurationEntity** genom att använda Excel-tillägget. För att använda tillägget, aktivera designläge i Ekonomi och Drift Excel-tillägget och lägg till **DualWriteProjectConfigurationEntity** till ett kalkylblad. Mer information finns i [Visa och uppdatera enhetsdata med Excel](../../office-integration/use-excel-add-in.md).
    2. Välj och ta bort posterna som har problem i mappningen och projektet för dubbelriktad skrivning. Det kommer att finnas två poster för varje mappning för dubbelriktad skrivning.
    3. Publicera ändringarna med hjälp av Excel-tillägget. Det här steget är viktigt eftersom det tar bort posterna från entiteten och de underliggande tabellerna.
    4. Bidra till att förhindra fel när du länkar om Ekonomi och Drift- eller Dataverse-miljön genom att se till att inga konfigurationer för dubbelriktad skrivning finns kvar.

## <a name="live-synchronization-error-after-you-do-a-full-database-copy"></a>Live-synkroniseringsfel när du har kopierat en fullständig databas

Du kanske får följande felmeddelande när du har kört en fullständig databaskopia från ett system till ett annat och sedan försöker köra en databasåtgärd:

*SecureConfig-organisation (???) matchar inte CRM-organisation (???).*

Felmeddelandet visas från plugin-programmet för körning av dubbelriktad skrivning för att säkerställa att konfigurationen för dubbelriktad skrivning som har konfigurerats i ett system inte kan användas i ett annat system.

Du löser problemet genom att radera alla poster i tabellen **msdyn_dualwriteruntimeconfig** när du har återställt databasen. Mer information finns i [Ta bort länkning och omlänkning av miljöer med dubbelriktad skrivning](relink-environments.md).

## <a name="live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps"></a>Problem med live-synkronisering som orsakas av fel frågefiltersyntax på mappningarna för dubbelriktad skrivning

Även om frågeuttrycket för ett mappningsfilter för dubbelriktad skrivning är syntaktiskt korrekt fungerar det kanske inte som förväntat. Filteruttrycket gäller för en entitet, inte för en enskild datakälla för ett frågeobjekt. Därför returnerar inte SQL-frågan som genereras de förväntade resultaten.

Här är ett exempel:

```dos
Query entity = PROJECTENTITY
Query expression = (ParentProject == "")
```

Du kanske förväntar dig att projekt som inte har någon överordnad ska filtreras bort. Filtret fungerar dock inte eftersom det översätts till en fråga som liknar följande exempel.

```sql
SELECT T1.RECID,T1.MODIFIEDDATETIME,T1.RECVERSION,T1.RECID,T1.DIMENSION,
T1.LOCATION,T1.PROJECTCONTROLLER,T1.PROJECTID,T1.PROJECTMANAGER,T1.REFERENCE,
T1.SALESMANAGER,T1.SCHEDULED,T1.RECVERSION#8,T1.RECVERSION#7,
T1.RECVERSION#6,T1.RECVERSION#5,T1.RECVERSION#4,T1.RECVERSION#3,
T1.RECVERSION#2,T1.RECID#8,T1.RECID#7,T1.RECID#6,T1.RECID#5,
T1.RECID#4,T1.RECID#3,T1.RECID#2,T1.PARTITION FROM PROJECTENTITY T1 
WHERE(((((((((((PARTITION=5637144576) AND (DATAAREAID=N'usmf')) AND 
((PARTITION#2=5637144576) OR (PARTITION#2 IS NULL))) AND 
((PARTITION#3=5637144576) OR (PARTITION#3 IS NULL))) AND 
((PARTITION#4=5637144576) OR (PARTITION#4 IS NULL))) AND 
((PARTITION#5=5637144576) OR (PARTITION#5 IS NULL))) AND 
((PARTITION#6=5637144576) OR (PARTITION#6 IS NULL))) AND 
((PARTITION#7=5637144576) OR (PARTITION#7 IS NULL))) AND 
((PARTITION#8=5637144576) OR (PARTITION#8 IS NULL))) AND 
((DATAAREAID#8=N'usmf') OR (DATAAREAID#8 IS NULL))) AND 
(PARENTPROJECT='')) 
ORDER BY T1.PROJECTID
```

Det verkliga resultatet är att fältet `parentProject` utvärderas till `null`. `null` är dock inte detsamma som den tomma strängen. På grund av den här felmatchningen returnerar frågefiltret inte giltiga resultat.

Gör så här om du vill åtgärda problemet.

1. Lägg till en beräknad kolumn som kan läggas till i en tilläggsmodell och som underbyggs av logik som konverterar `null` till den tomma strängen.

    ```dos
    SysComputedColumn::if(SysComputedColumn::isNullExpression(ParentProject), SysComputedColumn::returnLiteral(""), fieldName);
    ```

2. Använd filtret på den nya beräknade kolumnen i stället för på standardkolumnen.

Om du vill utvärdera filtret i en utvecklingsmiljö kan du använda följande X++-kod för att validera resultatet. Kör den här koden som ett fristående program. Du kan använda det för att utvärdera olika typer av filter som kan användas för en entitet innan du använder dessa filter på mappningar för dubbelriktad skrivning. Frågan kan köras mot databasen för att utvärdera avvikelser.

```xpp
var entityName = "PROJECTENTITY";
var filterExpression = '(ParentProject == "")';
Query query = new Query();
query.literals(NoYes::Yes); 
QueryBuildDataSource qbd = query.addDataSource(tablename2id(entityName));
qbd.addRange(fieldname2id(qbd.table(),identifierStr(RecVersion))).value(filterExpression);
qbd.addSelectionField(fieldname2id(qbd.table(),identifierStr(RecId)));
QueryRun qRun = new QueryRun(query);
// This provides the actual sql statement to execute
var actualSqlStatement = query.getSQLStatement();
while(qRun.next())
{
    var rec = qRun.get(tableName2Id(entityName));
}
```

## <a name="data-from-finance-and-operations-apps-isnt-synced-to-dataverse"></a>Data från Ekonomi och Drift-appar som inte är synkroniserade till Dataverse

Vid live-synkronisering kanske du stöter på ett problem där bara en del av data synkroniseras från Ekonomi och Drift-appar till Dataverse, eller att data inte synkroniseras alls.

> [!NOTE]
> Du måste åtgärda det här problemet under utvecklingen.

Innan du börjar åtgärda problemet måste du kontrollera följande förutsättningar:

+ Kontrollera att dina anpassade ändringar skrivs in i ett enda transaktionsdefinitionsområde.
+ Affärshändelser och ramverket för dubbelriktad skrivning hanterar inte åtgärderna `doinsert()`, `doUpdate()` och `recordset()`, eller poster där `skipBusinessEvents(true)` har markerats. Om din kod finns i de här funktionerna kommer dubbelriktad skrivning inte att utlösas.
+ Affärshändelser måste registreras för den datakälla som mappas. En del datakällor kan använda en yttre koppling och kan markeras som skrivskyddade i Ekonomi och Drift-appar. Dessa datakällor spåras inte.
+ Ändringar initieras endast om ändringarna gäller de mappade fälten. Omappade fältändringar utlöser inte dubbelriktad skrivning.
+ Se till att filterutvärderingarna ger ett giltigt resultat.

### <a name="troubleshooting-steps"></a>Felsökningssteg

1. Granska fältmappningar på administratörssidan för dubbelriktad skrivning. Om ett fält inte mappas från Ekonomi och Drift-appar till Dataverse spåras det inte. På följande bild spåras till exempel fältet **Beskrivning** från Dataverse, men inte från Ekonomi och Drift-appar. Inga ändringar i detta fält i Ekonomi och Drift-appar kommer att spåras.

    ![Spårat fält.](media/live-sync-troubleshooting-1.png)

2. Bestäm om datakällan är spårad i definitionen för affärshändelser. I följande illustration spåras till exempel inget fält från tabellen **DefaultDimensionDAVs** och underliggande tabeller för ändringar. Datakällor som använder en yttre koppling och som markeras som skrivskyddade spåras inte.

    ![Fält som inte spåras.](media/live-sync-troubleshooting-2.png)

3. Bestäm om de mappade tabellfälten ska visas i tabellen **BUSINESSEVENTSDEFINITION** på det sätt som visas i illustrationen nedan. Om du inte hittar fältet som du letar efter i frågeresultatet utlöses det inte av dubbelriktad skrivning.

    ![Spårat fält i tabellen.](media/live-sync-troubleshooting-3.png)

### <a name="sample-scenario"></a>Exempelscenario

I Ekonomi och Drift-appar finns det en uppdatering av adressen för en kontaktpost, men adressändringen synkroniseras inte till Dataverse. Detta scenario inträffar eftersom ingen post i tabellen **BusinessEventsDefinition** har kombinationen av den berörda tabellen och entiteten. Tabellen **LogisticsPostalAddress** är inte den direkta datakällan för entiteten **smmContactpersonCDSV2Entity**. Entiteten **smmContactpersonCDSV2Entity** har **smmContactPersonV2Entity** som datakälla, och **smmContactPersonV2Entity** har i sin tur **LogisticsPostalAddressBaseEntity** som datakälla. Tabellen **LogisticsPostalAddress** är datakällan för **LogisticsPostalAddressBaseEntity**.

En liknande situation kan uppstå i vissa icke-standardmönster, t.ex. i fall där tabellen som ändras i Ekonomi och Drift-appar inte är uppenbart länkad till den entitet som innehåller den. Primära adressdata beräknas till exempel på entiteten **smmContactPersonCDSV2Entity**. Ramverket för dubbelriktad skrivning försöker fastställa hur en ändring i en underliggande tabell mappas tillbaka till entiteter. Vanligtvis räcker det med att använda det här sättet. I vissa fall är dock länken så komplex att du måste vara specifik. Du måste se till att **RecId** för den relaterade tabellen är direkt tillgänglig för entiteten. Lägg sedan till en statisk metod för att övervaka tabellen för ändringar.

Se till exempel metoden **smmContactPersonCDSV2Entity::getEntityDataSourceToFieldMapping()**. **CustCustomerV3entity** och **VendVendorV2Entity** ändrats för att hantera den här situationen.

Gör så här om du vill åtgärda problemet.

1. Lägg till fältet **PrimaryPostalAddressRecId** i entiteten **smmContactPersonV2Entity**. Gör det internt.

    ![Fält som läggs till i smmContactPersonV2Entity-entiteten.](media/Troubleshoot_live_sync_issue_1.png)

2. Lägg till samma fält i entiteten **smmContactPersonCDSV2Entity**.

    ![Fält som läggs till i entiteten smmContactPersonCDSV2Entity.](media/Troubleshoot_live_sync_issue_2.png)

3. Lägg till följande metod till klassen **smmContactPersonCDSV2Entity**.

    ```xpp
    public static container getEntityDataSourceToFieldMapping(container mapping)
    {
        mapping += [[tablestr(smmContactPersonCDSV2Entity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)]];
        return mapping;
    }
    ```

4. Synkronisera databasen och bygg programmet.
5. Stoppa alla mappningar för dubbelriktad skrivning som har skapats i entiteten **smmContactPersonCDSV2Entity**.
6. Starta mappningen. Du bör se den nya tabellen (**LogisticsPostalAddress** i det här exemplet) som du har börjat spåra med hjälp av kolumnen **RefTableName** för den rad där värdet **refentityname** är lika med **smmContactPersonCDSV2Entity** i tabellen **BusinessEventsDefinition**.

## <a name="error-when-you-create-a-record-where-multiple-records-are-sent-from-a-finance-and-operations-app-to-dataverse-in-the-same-batch"></a>Fel när du skapar en post där flera poster skickas från en Ekonomi och Drift-app till Dataverse i samma batch

För alla transaktioner skapar en Ekonomi och Drift-app data i en batch och skickar dem som ett batchjobb till Dataverse. Om två poster skapas som en del av samma transaktion, och de refererar till varandra, kan du få ett felmeddelande som liknar följande exempel i Ekonomi och Drift-appen:

*Det gick inte att skriva data till aaa_fundingsources. Det gick inte att slå upp ebecsfs_contracts med värden {PC00...}. Det gick inte att slå upp aaa_fundingsources med värden {PC00...}. Skrivningar till aaa_fundingsources misslyckades med felmeddelandet Undantagsmeddelande: Fjärrservern returnerade ett fel: (400) Felaktig begäran.*

Du rättar till problemet genom att skapa entitetsrelationer i Ekonomi och Drift-appen för att visa att de två entiteterna är relaterade till varandra och att de relaterade posterna hanteras i samma transaktion.

## <a name="enable-verbose-logging-of-error-messages"></a>Aktivera utförlig loggning av felmeddelanden

I en Ekonomi och Drift-app kan du stöta på fel som hör till Dataverse-miljön. Felmeddelandet kanske inte innehåller den fullständiga texten i meddelandet eller andra relevanta data. Om du vill få mer information kan du aktivera utförlig loggning genom att ställa in flaggan **IsDebugMode** som finns i entiteten **DualWriteProjectConfigurationEntity** i alla projektkonfigurationer i Ekonomi och Drift-appar.

1. Öppna entiteten **DualWriteProjectConfigurationEntity** genom att använda Excel-tillägget. För att använda tillägget, aktivera designläge i Ekonomi och Drift Excel-tillägget och lägg till **DualWriteProjectConfigurationEntity** till ett kalkylblad. Mer information finns i [Visa och uppdatera enhetsdata med Excel](../../office-integration/use-excel-add-in.md).
2. Ställ in flaggan **IsDebugMode** på **Ja** i projektet.
3. Kör scenariot.
4. De utförliga loggarna finns i tabellen **DualWriteErrorLog**. Om du vill söka efter data med hjälp av tabellwebbläsaren använder du följande URL: `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`.
5. Om du vill samla in fler loggar i felsökningsläget ska du installera uppdateringen [KB 4595434 (Korrigering för tomma värden som sprids vid live-synkronisering av dubbelriktad skrivning)](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=c29ce15a80e6b3b4c01a722d9bdae1d7e71aa3662a044cfd0b765f736cfa98e9).

## <a name="error-when-you-add-an-address-for-a-customer-or-contact"></a>Fel när du lägger till en adress till en kund eller kontakt

Du kanske får följande felmeddelande när du försöker lägga till en adress för en kund eller kontakt i Ekonomi och Drift-appar eller Dataverse:

*Det gick inte att skriva data till msdyn_partypostaladdresses. Skrivningar till DirPartyPostalAddressLocationCDSEntity misslyckades med felmeddelande Begäran misslyckades med statuskoden BadRequest och CDS-felkod: 0x80040265-svarsmeddelande: Ett fel uppstod i plugin-programmet. En post med attributvärdena Plats-ID finns redan. För entitetsnyckeln Plats-ID krävs det att denna uppsättning attribut innehåller unika värden. Välj unika värden och försök igen.*

Du rättar till problemet genom att installera orkestreringsversion (2.2.2.60) för dubbelriktad skrivning så att nycklarna i tabellen **Adress** definieras så som visas i följande tabell.

| Egenskap | Värde |
|---|---|
| Visningsnamn | **Platsnyckel** |
| Namn | **msdyn_locationkey** |
| Fält | **msdyn_locationid**, **parentid** |
| Status | **Aktiva** |
| Systemjobb | Tom |

## <a name="error-when-you-add-a-customer-in-dataverse"></a>Fel när du lägger till en kund i Dataverse

Följande felmeddelande kan visas när du försöker lägga till en kund i en Dataverse:

*"RecordError0":"Skrivning misslyckades för entitetskunder V3 med okänt undantag – part-posten hittades inte för parttypen Organisation"} .*

När en kund skapas i Dataverse genereras ett nytt partsnummer. Felmeddelandet visas när kundposten, tillsammans med parten, synkroniseras med Ekonomi och Drift-appar, men det redan finns en kundpost som har ett annat partsnummer.

Du rättar till problemet genom att hitta efter kunden via sökning efter part. Skapa en ny kundpost om det inte finns någon post. Om kunden redan finns använder du den befintliga parten för att skapa den nya kundposten.

## <a name="error-when-you-create-a-new-customer-vendor-or-contact-in-dataverse"></a>Fel när du skapar en ny kund, leverantör eller kontakt i Dataverse

Du kanske får följande felmeddelande när du försöker skapa en ny kund, leverantör eller kontakt i Dataverse:

*Det går inte att uppdatera en parts typ från "DirOrganization" till "DirPerson". En borttagning av den befintliga parten följt av en infogning med den nya typen ska utföras i stället.*

I Dataverse finns det en nummerserie i tabellen **msdyn_party**. När ett konto skapas i Dataverse skapas en ny part (till exempel **Part-001** av typen **Organisation**). De här data skickas till Ekonomi och Drift-appen. Om Dataverse-miljön återställs eller om Ekonomi och Drift-miljön är kopplad till en annan Dataverse-miljö, och sedan skapas en ny kontaktpost i Dataverse, skapas ett nytt partvärde som börjar med **Part-001**. Den här gången blir partposten som skapas **Part-001** för typen **Person**. När dessa data synkroniseras visas föregående felmeddelande i Ekonomi och Drift-apparna eftersom partposten **Part-001** för typen **Organisation** redan finns.

Du rättar till problemet genom att ändra den automatiska nummerserien för fältet **msdyn_partynumber** för tabellen **msdyn_party** i Dataverse till en annan automatisk nummerserie.

## <a name="performance-issue-with-customer-or-contact-mappings"></a>Prestandaproblem med kund- eller kontaktmappningar

Du kan marginellt förbättra prestandan för live-synkronisering för kunder och kontakter genom att anpassa metoden **getEntityDataSourceToFieldMapping** (i entiteten **metoden CustCustomerV3Entity**) och metoden **getEntityDataSourceToFieldMapping** (i entiteten **smmContactPersonCDSV2Entity**). Dessa anpassningar minskar antalet poster i tabellen **BusinessEventsDefinition**. Den här reduktionen av antalet poster minskar i sin tur antalet händelser som utlöses.

Metoden **getEntityDataSourceToFieldMapping** i entiteten **CustCustomerV3Entity** ser till att en uppdatering av kundens elektroniska adress eller postadress utlöser affärshändelser, så att uppdaterade data skickas till Dataverse. Om du inte använder alla fält och inte behöver informationen i dubbelriktad skrivning kan du kommentera ut de relevanta raderna i metoden. Alla spårade fält och tabeller som läggs till i den här metoden lägger till en post i tabellen **BusinessEventsDefinition** table för kombinationen av spårad tabell och spårad entitet.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, AddressRecordId)],
        [identifierstr(DirPartyBaseEntity), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactURLRecordId)],
        [identifierstr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactPhoneRecordId)],
        [identifierstr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactEmailRecordId)],
        [identifierstr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactFaxRecordId)],
        [identifierstr(DirPartyBaseEntity4), tablenum(DirPartyLocation), fieldstr(CustCustomerV3Entity, DirPartyLocationRecordId)],
        [identifierstr(DirPartyBaseEntity5), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, InvoiceAddressRecordId)],
        [identifierstr(DirPartyBaseEntity6), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, DeliveryAddressRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(DirPartyTable), fieldstr(CustCustomerV3Entity, PartyRecordId)]];
    return mapping;
}
```

På liknande sätt ser metoden **getEntityDataSourceToFieldMapping** i entiteten **smmContactPersonCDSV2Entity** till att en uppdatering av kontaktens elektroniska adress eller postadress utlöser affärshändelser, så att uppdaterade data skickas till Dataverse. Med den här metoden kan du kommentera bort raderna för de fält som du inte använder.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)],
        [identifierStr(DirPartyBaseEntity), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PrimaryAddressLocation)],
        [identifierStr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactEmailRecordId)],
        [identifierStr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFaxRecordId)],
        [identifierStr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactPhoneRecordId)],
        [identifierStr(DirPartyBaseEntity4), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFacebookRecordId)],
        [identifierStr(DirPartyBaseEntity5), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTwitterRecordId)],
        [identifierStr(DirPartyBaseEntity6), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactURLRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactLinkedInRecordId)],
        [identifierStr(DirPartyBaseEntity8), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTelexRecordId)],
        [identifierStr(DirPartyBaseEntity9), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PartyRecordId)]];
    return mapping;
}
```

När du har uppdaterat metoderna följer du dessa steg.

1. Synkronisera databasen och bygg programmet.
2. Stoppa alla mappningar för dubbelriktad skrivning i entiteten **smmContactPersonCDSV2Entity** och **CustCustomerV3Entity**.
3. Starta mappningarna. Du bör se färre poster i entiteterna **smmContactPersonCDSV2Entity** och **CustCustomerV3Entity** och tabellen **BusinessEventsDefinition**, och prestandan kan förbättras marginellt.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
