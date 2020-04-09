---
title: Vanliga frågor om initiering med företagsdata
description: Hur du initierar Common Data Service eller andra Dynamics 365-appdata med företagsinformation innan du aktiverar dubbelriktad anslutning.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 1ed97d7c388347eb5afe101f51173b6d48b18fcd
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172933"
---
# <a name="bootstrap-with-company-data-faq"></a>Vanliga frågor om initiering med företagsdata
 
[!include [banner](../../includes/banner.md)]


## <a name="why-do-i-need-bootstrapping"></a>Varför måste jag använda initiering? 
Du kanske har en befintlig Common Data Service eller annan Dynamics 365-appinstans med affärsdata och du vill aktivera dubbelriktad anslutning mot den. I detta fall måste du initiera Common Data Service eller andra Dynamics 365-appdata med företagsinformation innan du aktiverar dubbelriktad anslutning.  
 
## <a name="when-should-i-use-bootstrapping"></a>När ska jag använda initiering? 
Du bör använda initieringsfunktionen för att aktivera dubbelriktade entitetsmappningar (under steg #5).  
1. Om du vill ställa in dubbelriktad anslutning mellan olika instanser av din Finance and Operations-app och Common Data Service eller andra Dynamics 365-appar, loggar du in på Finance and Operations-appen som administratör. 
2. Gå till modulen **datahantering** och klicka på knappen **dubbelriktad**. Då startas **dataintegratorn**. 
3. Skapa dubbelriktad anslutning för ett eller flera företag.  
    > [!div class="mx-imgBorder"]
    > ![Skapa dubbelriktad anslutning](media/dual-write-boot-1.png)
4. Aktivera entitetsmappningen **Cdm_companies**. Detta synkroniserar företag från Finance and Operations-appen till Common Data Service.  
    > [!div class="mx-imgBorder"]
    > ![Aktivera entitetsmappningen](media/dual-write-boot-2.png)
5. Kör exempelinitieringskoden på Common Data Service eller andra Dynamics 365-appinstanser.  
6. När initieringen är klar och systemet är klart för live-synkronisering aktiverar du entitetsmappningarna.  

    Om du aktiverar entitetsmappningarna utlöses den inledande datasynkroniseringen för de aktiverade entitetsmappningarna. De data som motsvarar de företag som valts för dubbelriktad anslutning synkroniseras mellan Finance and Operations-appen och Common Data Service. 
 
## <a name="how-to-i-use-the-code-sample"></a>Hur ska jag använda kodexemplet?
Exempelkoden är ett C#-program som du kan läsa in i Visual Studio. Det krävs NuGet-paketberoenden på Common Data Service SDK som du kan uppdatera via Visual Studio standardverktyg. 

När du har packat upp och öppnat lösningen i Visual Studio och återställt NuGet-paketen söker du efter **TODO** i koden. Varje beslut som du måste fatta om hur du vill initiera företagsinformation noteras genom **TODO** med exempelkod för en kanonisk implementering. 

Exempelkoden visar bara ett av många sätt som du kan kategorisera entitetsposter efter företag. Genom att ändra logiken i avsnitten **TODO** kan du skapa en anpassad kategorisering. 
 
## <a name="what-should-i-expect"></a>Vad ska jag förvänta mig?
Som standard kan du använda exempelprogrammet för att ange en ordlista med kodmappningar för affärsenhet till företag. Alla entiteter du initierar med fältet **OwningBusinessUnitOwningBusinessUnit** ställs automatiskt in på att använda det angivna företaget. Alla entiteter utan fältet **OwningBusinessUnit**, t.ex. produkt, ställer in företaget baserat på mappningen med ett tomt affärsenhetsvärde.

Konsolprogrammet förväntar sig en parameter, antingen **–simulera** eller **–tillämpa**. Om du använder kommandoradparametern **–simulera** uppdateras inga data. Endast **simulation_<entityname>.csv**-filer genereras i samma katalog som verktyget, en för varje entitet som skulle ha uppdaterats. Du kan granska dessa filer iterativt medan du arbetar för att säkerställa att koden uppdaterar företagsvärden som förväntat. 

När du är klar med de simulerade uppdateringarna använder du parametern **–tillämpa**. Detta uppdaterar alla poster som för närvarande har ett felaktigt företagsvärde i grupper om 1000 poster i taget (som standard). Koden är idempotent enligt det som anges, vilket innebär att du kan köra den igen och att endast de felaktigt tilldelade företagen uppdateras. När du kör med **–tillämpa** används kodutgångar CSV-filer av de ändringar som har gjorts, med namnet **applied_<entityname>.csv**. 

 ```csharp
 using Microsoft.Crm.Sdk.Messages;
using Microsoft.Xrm.Sdk;
using Microsoft.Xrm.Sdk.Messages;
using Microsoft.Xrm.Sdk.Query;
using Microsoft.Xrm.Tooling.Connector;
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.IO;

namespace BootstrapCompany
{
    /// <summary>
    /// Application to bootstrap the company field on existing records in CDS in preparation for integration to Finance and Operations.
    /// </summary>
    /// <remarks>
    /// This application assumes that the target companies already exist in the CDS environment in the cdm_Company table and are
    /// identified by their company code. It also assumes that the current owning business unit of each record should be used
    /// to categorize by company. This logic can easily be updated to utilize alternate sources of categorization including
    /// custom entities, teams, custom fields on tables, or any other data. This code is provided only as a sample. 
    /// 
    /// To utilize this code, update each of the locations currently denoted with a TODO statement.
    /// 
    /// This code is provided AS IS with no warranties or guarantees, and confers no rights.
    /// </remarks>
    public class Program
    {
        /// <summary>
        /// The number of records to query and update in CDS in a single operation.
        /// </summary>
        /// <remarks>
        /// The larger this number, the fewer calls will need to be made, so the faster the updates
        /// will complete. However, larger batch sizes are more likely to cause contention. Additionally,
        /// when SQL exceeds some threshold of locks (generally around 5,000), it will escalate to
        /// an entire table lock, which blocks all other activity in the live system on this table. As 
        /// such, a batch size of around 1,000 is relatively fast, while also relatively safe in terms
        /// of contention and transaction time.
        /// </remarks>
        const int requestBatchSize = 1000;

        /// <summary>
        /// The number of faults that may be seen in CDS before the operation is aborted and an exception is thrown.
        /// </summary>
        /// <remarks>
        /// An occassional error due to contention when updating large tables in production is expected, so by default
        /// errors are logged and skipped. However, if a large number of errors are seen, ignoring those errors
        /// in subsequent batches gets expensive, and is usually indicative of a larger issue that should be addressed
        /// before continuing. Faulted requests are *not* retried, but would be picked up in a subsequent run of this script.
        /// </remarks>
        const int maxFaultThreshold = 100;

        /// <summary>
        /// The maximum number of records per business unit to export when simulating.
        /// </summary>
        /// <remarks>
        /// During simulation, queries are not batched since doing so would require ordering and so be slightly
        /// different from the actual execution logic. To keep this the same between both paths, simulates are
        /// not batched and so a separate maximum number of records per business unit can be specified.
        /// </remarks>
        const int maxSimulateRecordsPerBusinessUnit = 10000;

        /// <summary>
        /// Whether or not operations should continue if any errors are encountered.
        /// </summary>
        /// <remarks>
        /// This is different than setting maxFaultThreshold = 0, since the first batch of updates will be processed
        /// together. If continueOnError is true and maxFaultThreshold is 0, it is possible that multiple errors may
        /// be encountered and at the same time some records successfully updated. In a healthy system when updating
        /// a higher number of records, an occasional spurious error is expected, so it is recommended this be left as true.
        /// </remarks>
        const bool continueOnError = true;

        #region private variables
        private static Dictionary<string, EntityReference> cachedCompanyReferences = new Dictionary<string, EntityReference>();
        #endregion

        /// <summary>
        /// The main execution loop of the program.
        /// </summary>
        /// <param name="args">No arguments are expected.</param>
        static void Main(string[] args)
        {
            if (args.Length != 1 && args[0] != "-simulate" && args[0] != "-apply")
            {
                Console.WriteLine("Usage: BootstrapCompany -simulate");
                Console.WriteLine("       BootstrapCompany -apply");
                Console.WriteLine("The -simulate flag will create a file called simulation.csv in the working");
                Console.WriteLine("directory, but will not change any data. The -apply flag will update live data");
                Console.WriteLine("in the same way that was demonstrated in the simulation.");

                return;
            }

            bool isSimulate = args[0].Equals("-simulate", StringComparison.OrdinalIgnoreCase);

            // Delete the simulation or applied files if existing
            foreach (string existingSimulate in Directory.EnumerateFiles(Directory.GetCurrentDirectory(), $"{(isSimulate ? "simulation" : "applied")}_*.csv"))
            {
                File.Delete(existingSimulate);
            }

            IOrganizationService orgService;

            // TODO: Provide your connection string details for your environment
            CrmServiceClient cdsConnection = new CrmServiceClient("AuthType=Office365;Username=youraliashere@yourdomainhere.com;Password=yourpasswordhere;URL=https://yourorganizationurlhere.crm.dynamics.com/;");
            orgService = (IOrganizationService)cdsConnection.OrganizationWebProxyClient != null ? (IOrganizationService)cdsConnection.OrganizationWebProxyClient : (IOrganizationService)cdsConnection.OrganizationServiceProxy;

            if (orgService != null)
            {
                // Get the current user ID to verify the connection was successful
                Guid userid = ((WhoAmIResponse)orgService.Execute(new WhoAmIRequest())).UserId;

                if (userid != Guid.Empty)
                {
                    Console.WriteLine("Connection Successful!");
                }

                // TODO: Provide a mapping of OwningBusinessUnit name to cdm_Company company ID. You can reuse
                // the same company ID for multiple business units if desired. In this example, it assumes that
                // the business unit named "USMF" is related to the company "USMF". If all records were owned
                // by the same root business unit, then the first field in the dictionary should be set to the 
                // name of the root business unit, usually the same value as the organization (eg, "Contoso").
                Dictionary<string, string> businessUnitToCompanyMapping = new Dictionary<string, string>()
                {
                    { "", "USMF" }, // The default mapping to use for any entity that doesn't have an owningbusinessunit field
                    { "USMF", "USMF" },
                    { "FRRT", "FRRT" },
                };

                // TODO: Provide a list of entities for which the company field should be backfilled based
                // on owning business unit. The list below represents all existing entities for which a cdm_Company
                // lookup field was added as part of the Finance and Operations dual write project.
                BatchUpdateEntity(orgService, "account", "msdyn_company", businessUnitToCompanyMapping, true, isSimulate, "accountnumber", "name");
                BatchUpdateEntity(orgService, "contact", "msdyn_company", businessUnitToCompanyMapping, true, isSimulate, "fullname");
                // ... Add more here

                // Note, the product entity does not have an owningbusinessunit field like most other entities, so
                // assigning company by Business Unit is not applicable. In this case, whichever mapping specifies an
                // empty business unit will be used to categorize entities without an owningbusinessunit field.
                BatchUpdateEntity(orgService, "product", "msdyn_companyid", businessUnitToCompanyMapping, false, isSimulate, "productnumber");
            }
            else
            {
                Console.WriteLine("Connection failed...");
            }

            Console.WriteLine("Done");
            Console.ReadLine();
        }

        /// <summary>
        /// Updates all incorrectly assigned company relationships for the specified entity.
        /// </summary>
        /// <param name="orgService">The connection to CDS.</param>
        /// <param name="entityName">The logical name of the entity to update.</param>
        /// <param name="companyFieldName">The physical name of the field in the entity being updated which contains the cdm_Company id.</param>
        /// <param name="businessUnitToCompanyMapping">A dictionary of business unit name to company code.</param>
        /// <param name="hasOwningBusinessUnit">true if the entity has an owningbusinessunit field; otherwise, false.</param>
        /// <param name="isSimulate">true to simulate output; otherwise, false.</param>
        /// <param name="fieldsToExport">A set of fields to export into a CSV for this entity if simulating.</param>
        /// <returns>true if the entity was successfully processed without any errors; otherwise, false.</returns>
        private static bool BatchUpdateEntity(
            IOrganizationService orgService, 
            string entityName, 
            string companyFieldName, 
            Dictionary<string, string> businessUnitToCompanyMapping, 
            bool hasOwningBusinessUnit, 
            bool isSimulate, 
            params string[] fieldsToExport)
        {
            List<Guid> faultedIds = new List<Guid>();
            int totalRecordsProcessed = 0;
            Stopwatch stopwatch = new Stopwatch();
            stopwatch.Start();

            string fileName = isSimulate ? "simulation" : "applied";
            StreamWriter simulationWriter = new StreamWriter(Path.Combine(Directory.GetCurrentDirectory(), $"{fileName}_{entityName}.csv"), true);
            simulationWriter.Write("EntityName,EntityId,");
            foreach (string fieldToExport in fieldsToExport)
            {
                simulationWriter.Write($"{fieldToExport},");
            }
            simulationWriter.WriteLine("BusinessUnit,NewCompanyId");

            // Process each mapped business unit individually
            foreach (string businessUnitName in businessUnitToCompanyMapping.Keys)
            {
                Console.WriteLine("Updating any {0} records for business unit {1} to company {2}...", entityName, businessUnitName, businessUnitToCompanyMapping[businessUnitName]);

                // The empty business unit value is only applicable for entities without an owning business unit field
                if (hasOwningBusinessUnit && string.IsNullOrEmpty(businessUnitName))
                {
                    continue;
                }
                else if (!hasOwningBusinessUnit && !string.IsNullOrEmpty(businessUnitName))
                {
                    continue;
                }

                var companyRef = GetCompanyReference(orgService, businessUnitToCompanyMapping[businessUnitName]);

                // Iteratively loop in batches to keep transaction lock size small
                bool moreRecordsExist = true;

                while (moreRecordsExist)
                {
                    moreRecordsExist = false;

                    // Find the first batch of records for this business unit with the wrong company ID. Ordering
                    // is not explicity specified, but SQL will most likely process based on the index starting with
                    // company ID, since all new company ID fields added for Finance and Operations integration have
                    // also added a new index starting with company ID. Explicitly specifying order would reduce the
                    // query plan options for SQL and introduce unnecessary overhead.
                    QueryExpression query = new QueryExpression(entityName);
                    query.ColumnSet.AddColumns(companyFieldName);
                    foreach (string fieldToExport in fieldsToExport)
                    {
                        query.ColumnSet.AddColumn(fieldToExport);
                    }
                    query.Criteria.AddCondition(companyFieldName, ConditionOperator.NotEqual, companyRef.Id);

                    // TODO: Uncomment the line below if you only want to fill in companies that are empty
                    // as opposed to the line above which updates the company any time it differs from the 
                    // desired value
                    // query.Criteria.AddCondition(companyFieldName, ConditionOperator.Equal, Guid.Empty);

                    if (isSimulate)
                    {
                        // During simulation, get as a single block of records to avoid positioning complexities
                        query.TopCount = maxSimulateRecordsPerBusinessUnit;
                    }
                    else
                    {
                        // Only batch records during actual application, otherwise retrieve all as a single operation
                        query.TopCount = requestBatchSize + faultedIds.Count;
                    }

                    // For entities with an owning business unit, join based on business unit name
                    if (hasOwningBusinessUnit)
                    {
                        // TODO: Replace this logic with different algorithms to determine the correct company
                        // in situations where business unit is not the best way to categorize.
                        LinkEntity linkEntity = query.AddLink("businessunit", "owningbusinessunit", "businessunitid", JoinOperator.Inner);
                        linkEntity.Columns.AddColumns("name");
                        linkEntity.LinkCriteria.AddCondition("name", ConditionOperator.Equal, businessUnitName);
                    }

                    var multipleRequest = new ExecuteMultipleRequest()
                    {
                        Settings = new ExecuteMultipleSettings()
                        {
                            ContinueOnError = true,
                            ReturnResponses = true
                        },
                        Requests = new OrganizationRequestCollection()
                    };

                    EntityCollection result = orgService.RetrieveMultiple(query);

                    int recordsAddedToBatch = 0;

                    foreach (var entity in result.Entities)
                    {
                        // Skip any previously faulted ID's. These values will be re-queried with each batch
                        // which is inefficient, but is more efficient than passing hundreds of ID values to 
                        // the underlying SQL query to be skipped at the database level (assuming the 
                        // max fault count is relatively small).
                        if (faultedIds.Contains(entity.Id))
                        {
                            continue;
                        }

                        entity.Attributes[companyFieldName] = companyRef;
                        
                        UpdateRequest updateRequest = new UpdateRequest()
                        {
                            Target = entity
                        };

                        simulationWriter.Write($"{entityName},{entity.Id},");
                        foreach (string fieldToExport in fieldsToExport)
                        {
                            simulationWriter.Write($"{entity.Attributes[fieldToExport]},");
                        }
                        simulationWriter.WriteLine($"{businessUnitName},{businessUnitToCompanyMapping[businessUnitName]}");

                        // Only add the update request when applying for real
                        if (!isSimulate)
                        {
                            multipleRequest.Requests.Add(updateRequest);
                        }

                        recordsAddedToBatch++;
                        Console.Write(".");
                    }

                    totalRecordsProcessed += recordsAddedToBatch;

                    if (recordsAddedToBatch > 0 && !isSimulate)
                    {
                        Console.Write("Sending {0} updates in a batch", recordsAddedToBatch);
                        var updateResult = orgService.Execute(multipleRequest) as ExecuteMultipleResponse;
                        moreRecordsExist = true;
                        Console.WriteLine(" done");

                        // If any faults are encountered, flag those IDs to not be processed again
                        // in subsequent batches.
                        if (updateResult.IsFaulted)
                        {
                            foreach (var response in updateResult.Responses)
                            {
                                if (response.Fault != null)
                                {
                                    Console.WriteLine(response.Fault);
                                    faultedIds.Add(((UpdateRequest)multipleRequest.Requests[response.RequestIndex]).Target.Id);

                                    if (faultedIds.Count > 100)
                                    {
                                        throw new ApplicationException("Excessive number of update failures, aborting operation");
                                    }
                                }
                            }
                        }
                    }
                    else
                    {
                        Console.WriteLine("No {0} records remain to be updated for {1}->{2}", entityName, businessUnitName, businessUnitToCompanyMapping[businessUnitName]);
                    }
                }
            }

            simulationWriter.Close();
            simulationWriter = null;

            stopwatch.Stop();
            Console.WriteLine("Processed {0} records for the {1} entity in {2}ms.", totalRecordsProcessed, entityName, stopwatch.ElapsedMilliseconds);

            return (faultedIds.Count == 0);
        }

        /// <summary>
        /// Gets an entity reference to the company with the specified ID if one exists.
        /// </summary>
        /// <param name="orgService">The CDS connection.</param>
        /// <param name="companyId">The company ID to search for.</param>
        /// <returns>An entity reference if one exists; otherwise, null.</returns>
        private static EntityReference GetCompanyReference(IOrganizationService orgService, string companyId)
        {
            if (cachedCompanyReferences.ContainsKey(companyId))
            {
                return cachedCompanyReferences[companyId];
            }

            QueryExpression query = new QueryExpression("cdm_company");
            query.ColumnSet.AddColumns("cdm_companyid");
            query.Criteria.AddCondition("cdm_companycode", ConditionOperator.Equal, companyId);
            query.TopCount = 1;

            EntityCollection result = orgService.RetrieveMultiple(query);

            EntityReference entityRef = null;

            foreach (var entity in result.Entities)
            {
                entityRef = entity.ToEntityReference();
                break;
            }

            cachedCompanyReferences[companyId] = entityRef;

            return entityRef;
        }
    }
}

 ```
 
 
