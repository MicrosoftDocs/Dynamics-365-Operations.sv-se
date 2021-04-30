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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8026abd5c3e0f9b78e8c016731fd7785490bc945
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891112"
---
# <a name="optimize-dataverse-virtual-table-queries"></a><span data-ttu-id="460f6-103">Optimera frågor för virtuell Dataverse-tabell</span><span class="sxs-lookup"><span data-stu-id="460f6-103">Optimize Dataverse virtual table queries</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="460f6-104">Utleverans</span><span class="sxs-lookup"><span data-stu-id="460f6-104">Issue</span></span>

### <a name="overview"></a><span data-ttu-id="460f6-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="460f6-105">Overview</span></span>

<span data-ttu-id="460f6-106">När virtuella Dataverse-register används för att utveckla integreringar och andra dataanslutningar med Dynamics 365 Human Resources kan du komma att uppleva prestandaproblem med frågor mot de virtuella registren.</span><span class="sxs-lookup"><span data-stu-id="460f6-106">When using Dataverse virtual tables to develop integrations and other data connections with Dynamics 365 Human Resources, you can experience performance issues with queries against the virtual tables.</span></span> <span data-ttu-id="460f6-107">Den långsamma frågekörningen kan uppstå mellan olika klienter eller gränssnitt.</span><span class="sxs-lookup"><span data-stu-id="460f6-107">The slow query execution can occur across various clients or interfaces.</span></span> <span data-ttu-id="460f6-108">Du kan till exempel komma att uppleva problemet under följande omständigheter:</span><span class="sxs-lookup"><span data-stu-id="460f6-108">For example, you may experience the issue in the following circumstances:</span></span>

- <span data-ttu-id="460f6-109">Vid förfrågan till ett virtuellt register via webb-API för Dataverse</span><span class="sxs-lookup"><span data-stu-id="460f6-109">When querying a virtual table through the Dataverse Web API</span></span>
- <span data-ttu-id="460f6-110">När du skapar en Power App mot ett virtuellt register</span><span class="sxs-lookup"><span data-stu-id="460f6-110">When creating a Power App against a virtual table</span></span>
- <span data-ttu-id="460f6-111">När du skapar en Power BI-rapport i ett virtuellt register</span><span class="sxs-lookup"><span data-stu-id="460f6-111">When building a Power BI report on a virtual table</span></span>

<span data-ttu-id="460f6-112">Samtliga dessa gränssnitt kan förorsaka prestandaproblemet.</span><span class="sxs-lookup"><span data-stu-id="460f6-112">All these interfaces have the potential to surface the performance issue.</span></span>

<span data-ttu-id="460f6-113">En orsak till långsam prestanda med virtuella Dataverse-register för Personal är kolumnerna för sekundärnycklar i det virtuella registret som relaterar till registrets [navigeringsegenskaper](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties).</span><span class="sxs-lookup"><span data-stu-id="460f6-113">One cause of slow performance with Dataverse virtual tables for Human Resources is the foreign key columns of the virtual table related to the table's [navigation properties](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties).</span></span> <span data-ttu-id="460f6-114">När navigeringsegenskaper skapas för ett virtuellt register läggs en kolumn för sekundärnycklar automatiskt till i registret i syfte att representera värdet på nyckeln för det relaterade virtuella registrets nyckelkolumn.</span><span class="sxs-lookup"><span data-stu-id="460f6-114">When navigation properties are created for a virtual table, a foreign key column is automatically added to the table to represent the value of the key for the related virtual table's key column.</span></span> <span data-ttu-id="460f6-115">Kolumnen **_mshr_fk_person_id_value** läggs exempelvis till i entiteten **mshr_hcmworkerbaseentity** med egenskapen för sekundärnyckel tillhörande entiteten **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="460f6-115">For example, the **_mshr_fk_person_id_value** column is added to the **mshr_hcmworkerbaseentity** entity with the foreign key property from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="460f6-116">På grund av hur värdena för dessa kolumner med sekundärnycklar bibehålls i ett register kan hämtningen av värden påverka prestandan för en fråga negativt mot det virtuella registret.</span><span class="sxs-lookup"><span data-stu-id="460f6-116">Because of how the values for these foreign key columns are maintained in a table, fetching the values can have a negative impact on the performance of a query against the virtual table.</span></span>

### <a name="potential-symptoms"></a><span data-ttu-id="460f6-117">Potentiella symptom</span><span class="sxs-lookup"><span data-stu-id="460f6-117">Potential symptoms</span></span>

<span data-ttu-id="460f6-118">Ett exempel där denna effekt kan komma att uppstå är i frågor som gäller enheten Arbetare **(mshr_hcmworkerentity)** eller Grundarbetare **(mshr_hcmworkerbaseentity)**.</span><span class="sxs-lookup"><span data-stu-id="460f6-118">An example where you may see this impact is in queries against the Worker (**mshr_hcmworkerentity**) or Base worker (**mshr_hcmworkerbaseentity**) entity.</span></span> <span data-ttu-id="460f6-119">Prestandaproblemet kan manifesteras på några olika sätt:</span><span class="sxs-lookup"><span data-stu-id="460f6-119">You may see the performance issue manifest itself in a few different ways:</span></span>

- <span data-ttu-id="460f6-120">**Långsam frågekörning:** Frågan mot det virtuella registret kan returnera förväntat resultat, men det tar längre tid än förväntat att köra frågan fullständigt.</span><span class="sxs-lookup"><span data-stu-id="460f6-120">**Slow query execution**: The query against the virtual table may return the expected results, but take longer than expected to complete execution of the query.</span></span>
- <span data-ttu-id="460f6-121">**Tidsgräns för fråga**: Frågan kan överskrida tidsgränsen och returnera följande fel: "En token erhölls i syfte att anropa Finance and Operations, men Finance and Operations returnerade ett fel av typen InternalServerError."</span><span class="sxs-lookup"><span data-stu-id="460f6-121">**Query timeout**: The query may time out and return the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type InternalServerError."</span></span>
- <span data-ttu-id="460f6-122">**Oväntat fel**: Frågan kan komma att returnera feltypen 400 med följande meddelande: "Ett oväntat fel har inträffat."</span><span class="sxs-lookup"><span data-stu-id="460f6-122">**Unexpected error**: The query may return an error type 400 with the following message: "An unexpected error occurred."</span></span>

  ![Feltyp 400 på HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType400.png)

- <span data-ttu-id="460f6-124">**Begränsning**: Frågan kan komma att överanvända serverresurser och drabbas av begränsningar.</span><span class="sxs-lookup"><span data-stu-id="460f6-124">**Throttling**: The query may overuse server resources, and become subject to throttling.</span></span> <span data-ttu-id="460f6-125">I det här fallet returnerar frågan följande felmeddelande: "En token anskaffades i syfte att anropa Finance and Operations, men Finance and Operations returnerade feltypen 429."</span><span class="sxs-lookup"><span data-stu-id="460f6-125">In this case, the query returns the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type 429."</span></span> <span data-ttu-id="460f6-126">Mer information om begränsning i Personal finns i [Frågor och avar om begränsningar](./hr-admin-integration-throttling-faq.md).</span><span class="sxs-lookup"><span data-stu-id="460f6-126">For more information in throttling in Human Resources, see [Throttling FAQ](./hr-admin-integration-throttling-faq.md).</span></span>

  ![Feltyp 429 på HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a><span data-ttu-id="460f6-128">Upplösning</span><span class="sxs-lookup"><span data-stu-id="460f6-128">Resolution</span></span>

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a><span data-ttu-id="460f6-129">Begränsa antalet kolumner som ingår i datafrågan</span><span class="sxs-lookup"><span data-stu-id="460f6-129">Limit the number of columns included in your data query</span></span>

<span data-ttu-id="460f6-130">Tillsammans med virtuella register är en av de metoder som har bäst potential att förbättra frågeprestandan att begränsa antalet kolumner som valts i frågan.</span><span class="sxs-lookup"><span data-stu-id="460f6-130">With virtual tables, one of the methods with the greatest potential to improve query performance is to limit the number of columns selected in the query.</span></span> <span data-ttu-id="460f6-131">Den allmänna vägledningen när du optimerar frågeprestandan är att begränsa kolumnerna som returneras i frågan till enbart de egenskaper du behöver.</span><span class="sxs-lookup"><span data-stu-id="460f6-131">The general guidance for optimizing query performance is to limit the columns returned in your query to only those properties that you need.</span></span> <span data-ttu-id="460f6-132">Detta gäller särskilt för kolumner med sekundärnycklar i virtuella register.</span><span class="sxs-lookup"><span data-stu-id="460f6-132">This is particularly true with the foreign key columns on virtual tables.</span></span> <span data-ttu-id="460f6-133">Om du inte behöver värdena i sekundärnyckelkolumnerna för din integration eller rapport, strukturerar du frågan så att den bara väljer de kolumner du behöver, exklusive sekundärnyckelkolumnerna.</span><span class="sxs-lookup"><span data-stu-id="460f6-133">If you don't need the values in the foreign key columns for your integration or report, then structure the query to select only the columns you need, excluding the foreign key columns.</span></span>

#### <a name="selecting-columns-in-an-odata-query"></a><span data-ttu-id="460f6-134">Välja kolumner i en OData-fråga</span><span class="sxs-lookup"><span data-stu-id="460f6-134">Selecting columns in an OData query</span></span>

<span data-ttu-id="460f6-135">När du frågar ett virtuellt register via webb-API:t för Dataverse kan du begränsa antalet kolumner som ingår i frågan genom att använda frågealternativet **$select** och definiera de kolumner som du behöver returnera resultat för.</span><span class="sxs-lookup"><span data-stu-id="460f6-135">When querying a virtual table through the Dataverse Web API, you can limit the number of columns included in the query by using the **$select** system query option, and define the columns for which you need results returned.</span></span> <span data-ttu-id="460f6-136">Du maximerar prestandan genom att utesluta kolumner med sekundärnycklar (de med prefixet **_mshr_FK_**) från frågan.</span><span class="sxs-lookup"><span data-stu-id="460f6-136">To maximize performance, exclude foreign key columns (those with the **_mshr_FK_** prefix) from the query.</span></span>

<span data-ttu-id="460f6-137">Följande fråga mot entiteten **mshr_hcmworkerbaseentity** kommer exempelvis endast att omfatta de kolumner som inkluderas i frågealternativsatsen **$select**, och alltså exkludera värden för sekundärnycklar.</span><span class="sxs-lookup"><span data-stu-id="460f6-137">For example, the following query against the **mshr_hcmworkerbaseentity** entity will include only the columns included in the **$select** query option clause, excluding foreign key values.</span></span> <span data-ttu-id="460f6-138">Detta ger betydande prestandaförbättringar jämfört med en fråga som omfattar alla registerkolumner.</span><span class="sxs-lookup"><span data-stu-id="460f6-138">This provides significant improvements in performance over a query that includes all table columns.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="460f6-139">Rekommendationen att begränsa antalet kolumner som har valts gäller även när du använder frågealternativet **$expand** för att expandera frågan till relaterade virtuella register med navigeringsegenskaper.</span><span class="sxs-lookup"><span data-stu-id="460f6-139">The recommendation to limit the number of columns selected also applies when using the **$expand** query option to expand the query to related virtual tables through navigation properties.</span></span> <span data-ttu-id="460f6-140">I följande fråga ingår till exempel kolumner från entiteten **mshr_hcmworkerbaseentity** med expanderade kolumner från entiteten **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="460f6-140">For example, the following query includes columns from the **mshr_hcmworkerbaseentity** entity with expanded columns from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="460f6-141">Notera att frågealternativet **$select** också ingår i frågealternativsatsen **$expand**.</span><span class="sxs-lookup"><span data-stu-id="460f6-141">Note that the **$select** query option is also included in the **$expand** query option clause.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="460f6-142">När du använder denna metod för hämtning av data med frågealternativet **$select** i frågealternatiovsatsen **$expand** visas vanligtvis större prestandaförbättringar när navigeringsegenskapen mellan enheterna är en fler-till-en-relation.</span><span class="sxs-lookup"><span data-stu-id="460f6-142">When using this method of retrieving data with the **$select** query option in the **$expand** query option clause, you will typically see greater performance improvements when the navigation property between the entities is a many-to-one relationship.</span></span> <span data-ttu-id="460f6-143">Du kanske inte ser samma minskning i frågekörningstiden när du utökar en en-till-många-relation.</span><span class="sxs-lookup"><span data-stu-id="460f6-143">You may not see the same decrease in query execution time when expanding a one-to-many relationship.</span></span> <span data-ttu-id="460f6-144">Mer information om relationsdefinitioner för virtuella Dataverse-register finns i [Registerrelationer](/powerapps/maker/data-platform/create-edit-entity-relationships).</span><span class="sxs-lookup"><span data-stu-id="460f6-144">For more information on relationship definition for Dataverse virtual tables, see [Table relationships](/powerapps/maker/data-platform/create-edit-entity-relationships).</span></span>

<span data-ttu-id="460f6-145">Mer information om hur du använder alternativen **$select** och **$expand** för systemfrågeställningar i webb-API för Dataverse finns i [Hämta relaterade entitetsposter med en frågeställning](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span><span class="sxs-lookup"><span data-stu-id="460f6-145">For more information on using the **$select** and **$expand** system query options in the Dataverse Web API, see [Retrieve related entity records with a query](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span></span>

#### <a name="selecting-columns-in-power-bi"></a><span data-ttu-id="460f6-146">Välja kolumner i Power BI</span><span class="sxs-lookup"><span data-stu-id="460f6-146">Selecting columns in Power BI</span></span>

<span data-ttu-id="460f6-147">Om du upplever något av ovannämnda tecken på sämre prestanda när du skapar en Power BI-rapport för ett virtuellt Dataverse-register kan du förbättra prestandan genom att exkludera kolumner med sekundärnycklar från de kolumner som valts för rapporten i registret.</span><span class="sxs-lookup"><span data-stu-id="460f6-147">If you experience any of the aforementioned indications of slow performance when building a Power BI report against a Dataverse virtual table, you can improve the performance by excluding foreign key columns from the columns selected from the table for the report.</span></span> <span data-ttu-id="460f6-148">Om du till exempel använder Power BI Desktop för att skapa en rapport för entiteten **mshr_hcmworkerbaseentity** kan du använda följande steg för att välja de kolumner som du vill inkludera i rapportfrågeställningen.</span><span class="sxs-lookup"><span data-stu-id="460f6-148">For example, if you are using Power BI Desktop to create a report against the **mshr_hcmworkerbaseentity** entity, you can use the following steps to select the columns you want included in the report query.</span></span>

1. <span data-ttu-id="460f6-149">I Power BI Desktop väljer du **Mer...** i listrutan **Hämta data** för åtgärdsmenyfliken.</span><span class="sxs-lookup"><span data-stu-id="460f6-149">In Power BI Desktop, select **More...** from the **Get data** drop-down list on the action ribbon.</span></span>
2. <span data-ttu-id="460f6-150">I fönstret **Hämta data** anger du **Common Data Service** i sökrutan, väljer kopplingen **Common Data Service** och sedan **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="460f6-150">In the **Get Data** window, enter **Common Data Service** in the search box, select the **Common Data Service** connector, and select **Connect**.</span></span>
3. <span data-ttu-id="460f6-151">I fältet **Server-URL** tillhörande fönstret Common Data Service anger du URI för din Dataverse-miljlö och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="460f6-151">In the **Server Url** field of the Common Data Service window, enter the organization URI for your Dataverse environment, and select **OK**.</span></span>
  
   ![Ange URI för din Dataverse-miljö](./media/PowerBIDataverseURLSetup.png)
  
4. <span data-ttu-id="460f6-153">Expandera noden **Entiteter** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="460f6-153">In the Navigator window, expand the **Entities** node.</span></span>
5. <span data-ttu-id="460f6-154">I sökrutan anger du **mshr_hcmworkerbaseentity** och väljer sedan entiteten.</span><span class="sxs-lookup"><span data-stu-id="460f6-154">In the search box, enter **mshr_hcmworkerbaseentity**, and select the entity.</span></span>
6. <span data-ttu-id="460f6-155">Välj **Transformera data**.</span><span class="sxs-lookup"><span data-stu-id="460f6-155">Select **Transform Data**.</span></span>
7. <span data-ttu-id="460f6-156">Välj **Avancerad redigerare** i Power Query-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="460f6-156">In the Power Query Editor window, select **Advanced Editor**.</span></span>
8. <span data-ttu-id="460f6-157">I fönstret **Avancerad redigerare** uppdaterar du frågeställningen enligt nedan och lägger till eller tar bort kolumner i matrisen efter behov.</span><span class="sxs-lookup"><span data-stu-id="460f6-157">In the **Advanced Editor** window, update the query to look like the below, adding or removing any columns to the array as needed.</span></span>

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Uppdatera frågeställningen i Advanced Editor för Power Query-redigeraren](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. <span data-ttu-id="460f6-159">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="460f6-159">Select **Done**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="460f6-160">Om du tidigare fått ett felmeddelande av typen 429 från frågeställningen före uppdatering kanske du måste vänta in en period för förnyat försök innan du uppdaterar frågeställningen så att den kan slutföras.</span><span class="sxs-lookup"><span data-stu-id="460f6-160">If you previously received an error of type 429 from the query prior to updating, you may need to wait for the retry period prior to refreshing the query for it to complete successully.</span></span>

10. <span data-ttu-id="460f6-161">Klicka på **Stäng & använd** i åtgärdsmenyfliken för Power Query-redigeraren.</span><span class="sxs-lookup"><span data-stu-id="460f6-161">Click **Close & Apply** on the Power Query Editor action ribbon.</span></span>

<span data-ttu-id="460f6-162">Du kan sedan börja skapa din Power BI-rapport baserat på kolumnerna som markerats i det virtuella registret.</span><span class="sxs-lookup"><span data-stu-id="460f6-162">You're then able to begin building your Power BI report against the columns selected from the virtual table.</span></span>

#### <a name="selecting-columns-in-power-apps"></a><span data-ttu-id="460f6-163">Välja kolumner i Power Apps</span><span class="sxs-lookup"><span data-stu-id="460f6-163">Selecting columns in Power Apps</span></span>

<span data-ttu-id="460f6-164">Du kan förbättra frågeställningsprestandan för Power Apps baserat på virtuella Dataverse-register genom att - liknande för webb-API-frågeställningar för Dataverse och Power BI - exkludera kolumner tillhörande relaterade register från din app.</span><span class="sxs-lookup"><span data-stu-id="460f6-164">Similar to Dataverse Web API queries and Power BI, you can improve query performance for Power Apps based on Dataverse virtual tables by excluding columns of related tables from your app.</span></span> <span data-ttu-id="460f6-165">Om några kolumner från ett relaterat register har inkluderats på en sida kommer den URL-adress för begäran som skapas för att hämta data att innehålla egenskaper för sekundärnyckel för det relaterade registret.</span><span class="sxs-lookup"><span data-stu-id="460f6-165">If any columns from a related table have been included on a page, then the request URL constructed to fetch the data will include foreign key properties of the related table.</span></span> <span data-ttu-id="460f6-166">Detta sänker prestandan genom att förorsaka ytterligare datasökningar på samma sätt som i exemplen i [Välja kolumner i en OData-frågeställning](#selecting-columns-in-power-apps) ovan.</span><span class="sxs-lookup"><span data-stu-id="460f6-166">This, as in the examples of [Selecting columns in an OData Query](#selecting-columns-in-power-apps) above, reduces performance by causing additional data lookups.</span></span>

<span data-ttu-id="460f6-167">För att kringgå detta kan du validera att inga datafält från relaterade register har inkluderats i några som helst dataformulär i ditt Power App.</span><span class="sxs-lookup"><span data-stu-id="460f6-167">To work around this, you can validate that no data fields from related tables have been included on any data form of your Power App.</span></span>

1. <span data-ttu-id="460f6-168">Välj dataformuläret för vyn i trädvisningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="460f6-168">In the Tree view pane, select the data form for the screen.</span></span>
2. <span data-ttu-id="460f6-169">I fönstret **Egenskaper** väljer du **Redigera** i egenskapen **Fält**.</span><span class="sxs-lookup"><span data-stu-id="460f6-169">In the **Properties** pane, select **Edit** on the **Fields** property.</span></span>
3. <span data-ttu-id="460f6-170">Se till att inga markerade fält tillhör datakällans virtuella register i fönstret **Data**.</span><span class="sxs-lookup"><span data-stu-id="460f6-170">In the **Data** pane, verify that none of the selected fields are fields of the virtual table of the data source.</span></span>

<span data-ttu-id="460f6-171">Om till exempel ett av datafälten som finns på en sida i programmet refererar till ett annat register, till exempel **ThisItem.Worker.Name**, där **Worker** är associerat register, kan prestandan försämras i samband med datahämtningen.</span><span class="sxs-lookup"><span data-stu-id="460f6-171">For example, if one of the data fields included on a page in the app references another table, such as **ThisItem.Worker.Name**, where **Worker** is the related table, there is a potential for reduced performance in fetching the data.</span></span>

<span data-ttu-id="460f6-172">Du kan använda [Power Apps-övervakaren](/powerapps/maker/monitor-overview) i syfte att säkerställa att bara de kolumner du behöver inkluderas i frågeställningen med avsikt att hämta data till Power App.</span><span class="sxs-lookup"><span data-stu-id="460f6-172">You can use the [Power Apps Monitor](/powerapps/maker/monitor-overview) to ensure that only the columns you need are being included in the query to get the data for the Power App.</span></span> <span data-ttu-id="460f6-173">Du kan visa den URL som skapats för åtgärden getRows i syfte att se till att de kolumner du har valt för programmet blir de optimala för hämtning av data.</span><span class="sxs-lookup"><span data-stu-id="460f6-173">You can view the URL constructed for the getRows operation to ensure the columns you have selected for your app will be optimal for retrieving the data.</span></span>

![Använd Power Apps-övervakaren när du vill analysera åtgärden getData](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a><span data-ttu-id="460f6-175">Filtrera datafrågeställningen</span><span class="sxs-lookup"><span data-stu-id="460f6-175">Filtering the data query</span></span>

<span data-ttu-id="460f6-176">En annan metod för att förbättra körningsprestandan i samband med frågeställningar är att begränsa antalet poster som returneras i frågeställningsresultaten.</span><span class="sxs-lookup"><span data-stu-id="460f6-176">Another method for improving query execution performance is to limit the number of records returned in the query results.</span></span> <span data-ttu-id="460f6-177">Detta gör du genom att filtrera resultaten så att du bara får de poster du behöver.</span><span class="sxs-lookup"><span data-stu-id="460f6-177">You can do this by filtering the results to ensure that you are only receiving the records you need.</span></span>

<span data-ttu-id="460f6-178">Se [Filtrera resultat](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) för mer information om hur du filtrerar frågeställningsdata.</span><span class="sxs-lookup"><span data-stu-id="460f6-178">See [Filter results](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) for more information on filtering query data.</span></span>

### <a name="limiting-the-page-size-of-the-query"></a><span data-ttu-id="460f6-179">Begränsa sidstorleken för frågeställningen</span><span class="sxs-lookup"><span data-stu-id="460f6-179">Limiting the page size of the query</span></span>

<span data-ttu-id="460f6-180">Om du arbetar med stora datauppsättningar kan du dela upp frågeställningsresultaten på flera sidor genom att lägga till preferensrubriken `odata.maxpagesize` i dataförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="460f6-180">If you're working with large data sets, you can divide query results into multiple pages by adding the `odata.maxpagesize` preference header to data queries.</span></span>

<span data-ttu-id="460f6-181">Mer information om sidnumrering finns i [Ange antalet entiteter som ska returneras på en sida](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span><span class="sxs-lookup"><span data-stu-id="460f6-181">For more information on paging, see [Specify the number of entities to return in a page](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span></span>

## <a name="see-also"></a><span data-ttu-id="460f6-182">Se även</span><span class="sxs-lookup"><span data-stu-id="460f6-182">See also</span></span>

- [<span data-ttu-id="460f6-183">Konfigurera virtuella Dataverse-register</span><span class="sxs-lookup"><span data-stu-id="460f6-183">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)
- [<span data-ttu-id="460f6-184">Vanliga frågor och svar om virtuella register i Personal</span><span class="sxs-lookup"><span data-stu-id="460f6-184">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)
- [<span data-ttu-id="460f6-185">Vanliga frågor och svar om begränsning</span><span class="sxs-lookup"><span data-stu-id="460f6-185">Throttling FAQ</span></span>](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]