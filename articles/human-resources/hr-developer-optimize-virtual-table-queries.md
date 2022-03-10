---
title: Optimera frågor för virtuell Dataverse-tabell
description: Optimera och felsöka prestanda hos frågeställningar i virtuella Dataverse-register
author: andreabichsel
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1857d2e35e369bcd0c8f02a059a307f31da8b3b9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067464"
---
# <a name="optimize-dataverse-virtual-table-queries"></a>Optimera frågor för virtuell Dataverse-tabell


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



## <a name="issue"></a>Utleverans

### <a name="overview"></a>Översikt

När virtuella Dataverse-register används för att utveckla integreringar och andra dataanslutningar med Dynamics 365 Human Resources kan du komma att uppleva prestandaproblem med frågor mot de virtuella registren. Den långsamma frågekörningen kan uppstå mellan olika klienter eller gränssnitt. Du kan till exempel komma att uppleva problemet under följande omständigheter:

- Vid förfrågan till ett virtuellt register via webb-API för Dataverse
- När du skapar en Power App mot ett virtuellt register
- När du skapar en Power BI-rapport i ett virtuellt register

Samtliga dessa gränssnitt kan förorsaka prestandaproblemet.

En orsak till långsam prestanda med virtuella Dataverse-register för Personal är kolumnerna för sekundärnycklar i det virtuella registret som relaterar till registrets [navigeringsegenskaper](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties). När navigeringsegenskaper skapas för ett virtuellt register läggs en kolumn för sekundärnycklar automatiskt till i registret i syfte att representera värdet på nyckeln för det relaterade virtuella registrets nyckelkolumn. Kolumnen **_mshr_fk_person_id_value** läggs exempelvis till i entiteten **mshr_hcmworkerbaseentity** med egenskapen för sekundärnyckel tillhörande entiteten **mshr_dirpersonentity**. På grund av hur värdena för dessa kolumner med sekundärnycklar bibehålls i ett register kan hämtningen av värden påverka prestandan för en fråga negativt mot det virtuella registret.

### <a name="potential-symptoms"></a>Potentiella symptom

Ett exempel där denna effekt kan komma att uppstå är i frågor som gäller enheten Arbetare **(mshr_hcmworkerentity)** eller Grundarbetare **(mshr_hcmworkerbaseentity)**. Prestandaproblemet kan manifesteras på några olika sätt:

- **Långsam frågekörning:** Frågan mot det virtuella registret kan returnera förväntat resultat, men det tar längre tid än förväntat att köra frågan fullständigt.
- **Tidsgräns för fråga**: Frågan kan timeout och returnera följande fel: "En token erhölls för att anropa Ekonomi och Drift, men Ekonomi och Drift returnerade ett fel av typen InternalServerError."
- **Oväntat fel**: Frågan kan komma att returnera feltypen 400 med följande meddelande: "Ett oväntat fel har inträffat."

  ![Feltyp 400 på HcmWorkerBaseEntity.](./media/HcmWorkerBaseEntityErrorType400.png)

- **Begränsning**: Frågan kan komma att överanvända serverresurser och drabbas av begränsningar. I det här fallet returnerar frågan följande fel: "En token erhölls för att anropa Ekonomi och Drift, men Ekonomi och Drift returnerade ett fel av typen 429." Mer information om begränsning i Personal finns i [Frågor och avar om begränsningar](./hr-admin-integration-throttling-faq.md).

  ![Feltyp 429 på HcmWorkerBaseEntity.](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a>Lösning

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a>Begränsa antalet kolumner som ingår i datafrågan

Tillsammans med virtuella register är en av de metoder som har bäst potential att förbättra frågeprestandan att begränsa antalet kolumner som valts i frågan. Den allmänna vägledningen när du optimerar frågeprestandan är att begränsa kolumnerna som returneras i frågan till enbart de egenskaper du behöver. Detta gäller särskilt för kolumner med sekundärnycklar i virtuella register. Om du inte behöver värdena i sekundärnyckelkolumnerna för din integration eller rapport, strukturerar du frågan så att den bara väljer de kolumner du behöver, exklusive sekundärnyckelkolumnerna.

#### <a name="selecting-columns-in-an-odata-query"></a>Välja kolumner i en OData-fråga

När du frågar ett virtuellt register via webb-API:t för Dataverse kan du begränsa antalet kolumner som ingår i frågan genom att använda frågealternativet **$select** och definiera de kolumner som du behöver returnera resultat för. Du maximerar prestandan genom att utesluta kolumner med sekundärnycklar (de med prefixet **_mshr_FK_**) från frågan.

Följande fråga mot entiteten **mshr_hcmworkerbaseentity** kommer exempelvis endast att omfatta de kolumner som inkluderas i frågealternativsatsen **$select**, och alltså exkludera värden för sekundärnycklar. Detta ger betydande prestandaförbättringar jämfört med en fråga som omfattar alla registerkolumner.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

Rekommendationen att begränsa antalet kolumner som har valts gäller även när du använder frågealternativet **$expand** för att expandera frågan till relaterade virtuella register med navigeringsegenskaper. I följande fråga ingår till exempel kolumner från entiteten **mshr_hcmworkerbaseentity** med expanderade kolumner från entiteten **mshr_dirpersonentity**. Notera att frågealternativet **$select** också ingår i frågealternativsatsen **$expand**.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

När du använder denna metod för hämtning av data med frågealternativet **$select** i frågealternatiovsatsen **$expand** visas vanligtvis större prestandaförbättringar när navigeringsegenskapen mellan enheterna är en fler-till-en-relation. Du kanske inte ser samma minskning i frågekörningstiden när du utökar en en-till-många-relation. Mer information om relationsdefinitioner för virtuella Dataverse-register finns i [Registerrelationer](/powerapps/maker/data-platform/create-edit-entity-relationships).

Mer information om hur du använder alternativen **$select** och **$expand** för systemfrågeställningar i webb-API för Dataverse finns i [Hämta relaterade entitetsposter med en frågeställning](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).

#### <a name="selecting-columns-in-power-bi"></a>Välja kolumner i Power BI

Om du upplever något av ovannämnda tecken på sämre prestanda när du skapar en Power BI-rapport för ett virtuellt Dataverse-register kan du förbättra prestandan genom att exkludera kolumner med sekundärnycklar från de kolumner som valts för rapporten i registret. Om du till exempel använder Power BI Desktop för att skapa en rapport för entiteten **mshr_hcmworkerbaseentity** kan du använda följande steg för att välja de kolumner som du vill inkludera i rapportfrågeställningen.

1. I Power BI Desktop väljer du **Mer...** i listrutan **Hämta data** för åtgärdsmenyfliken.
2. I fönstret **Hämta data** anger du **Common Data Service** i sökrutan, väljer kopplingen **Common Data Service** och sedan **Anslut**.
3. I fältet **Server-URL** tillhörande fönstret Common Data Service anger du URI för din Dataverse-miljlö och sedan **OK**.
  
   ![Ange URI för din Dataverse-miljö.](./media/PowerBIDataverseURLSetup.png)
  
4. Expandera noden **Entiteter** i navigeringsfönstret.
5. I sökrutan anger du **mshr_hcmworkerbaseentity** och väljer sedan entiteten.
6. Välj **Transformera data**.
7. I Power Query redigerarfönster, välj **Avancerad redigerare**.
8. I fönstret **Avancerad redigerare** uppdaterar du frågeställningen enligt nedan och lägger till eller tar bort kolumner i matrisen efter behov.

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Uppdatera frågeställningen i Avancerad redigerare för Power Query-redigeraren.](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. Välj **Klar**.

   > [!NOTE]
   > Om du tidigare fått ett felmeddelande av typen 429 från frågeställningen före uppdatering kanske du måste vänta in en period för förnyat försök innan du uppdaterar frågeställningen så att den kan slutföras.

10. Klicka på **Stäng & använd** i åtgärdsmenyfliken för Power Query-redigeraren.

Du kan sedan börja skapa din Power BI-rapport baserat på kolumnerna som markerats i det virtuella registret.

#### <a name="selecting-columns-in-power-apps"></a>Välja kolumner i Power Apps

Du kan förbättra frågeställningsprestandan för Power Apps baserat på virtuella Dataverse-register genom att - liknande för webb-API-frågeställningar för Dataverse och Power BI - exkludera kolumner tillhörande relaterade register från din app. Om några kolumner från ett relaterat register har inkluderats på en sida kommer den URL-adress för begäran som skapas för att hämta data att innehålla egenskaper för sekundärnyckel för det relaterade registret. Detta sänker prestandan genom att förorsaka ytterligare datasökningar på samma sätt som i exemplen i [Välja kolumner i en OData-frågeställning](#selecting-columns-in-power-apps) ovan.

För att kringgå detta kan du validera att inga datafält från relaterade register har inkluderats i några som helst dataformulär i ditt Power App.

1. Välj dataformuläret för vyn i trädvisningsfönstret.
2. I fönstret **Egenskaper** väljer du **Redigera** i egenskapen **Fält**.
3. Se till att inga markerade fält tillhör datakällans virtuella register i fönstret **Data**.

Om till exempel ett av datafälten som finns på en sida i programmet refererar till ett annat register, till exempel **ThisItem.Worker.Name**, där **Worker** är associerat register, kan prestandan försämras i samband med datahämtningen.

Du kan använda [Power Apps-övervakaren](/powerapps/maker/monitor-overview) i syfte att säkerställa att bara de kolumner du behöver inkluderas i frågeställningen med avsikt att hämta data till Power App. Du kan visa den URL som skapats för åtgärden getRows i syfte att se till att de kolumner du har valt för programmet blir de optimala för hämtning av data.

![Använd Power Apps-övervakaren när du vill analysera åtgärden getData.](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a>Filtrera datafrågeställningen

En annan metod för att förbättra körningsprestandan i samband med frågeställningar är att begränsa antalet poster som returneras i frågeställningsresultaten. Detta gör du genom att filtrera resultaten så att du bara får de poster du behöver.

Se [Filtrera resultat](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) för mer information om hur du filtrerar frågeställningsdata.

### <a name="limiting-the-page-size-of-the-query"></a>Begränsa sidstorleken för frågeställningen

Om du arbetar med stora datauppsättningar kan du dela upp frågeställningsresultaten på flera sidor genom att lägga till preferensrubriken `odata.maxpagesize` i dataförfrågningar.

Mer information om sidnumrering finns i [Ange antalet entiteter som ska returneras på en sida](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).

## <a name="see-also"></a>Se även

- [Konfigurera virtuella Dataverse-register](hr-admin-integration-common-data-service-virtual-entities.md)
- [Vanliga frågor och svar om virtuella register i Personal](hr-admin-virtual-entity-faq.md)
- [Vanliga frågor och svar om begränsning](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
