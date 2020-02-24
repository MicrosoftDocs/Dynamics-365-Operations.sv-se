När du kopierar en databas mellan olika miljöer måste du köra miljöetableringsverktyget igen innan den kopierade databasen fungerar helt och hållet och alla Commerce-komponenter är uppdaterade.

> [!IMPORTANT]
> Vi rekommenderar att du kör den här proceduren oavsett om du använder Commerce-komponenter eller inte, eftersom Commerce-funktionerna ingår i alla miljöer. 

Innan du fortsätter måste du se till att följande förutsättningar är uppfyllda:
1. Om du uppgraderar till juliversionen 2017 (även kallad 7.2) 7.2.11792.56024 installerar du följande X++-snabbkorrigeringar för appar i målmiljön innan du kör datauppgraderingen i den miljön. Detta förhindrar att olika fel uppstår under datauppgraderingen:

    - KB 4036156 - Mindre versionsuppgradering för Retail - Ingen variantnummerserie har ställts in. I detta korrigeringspaket ingår även KB 4035399 och KB 4035751. Observera att du måste ha minst Platform Update 9 för att kunna använda det här paketet. Installera de senaste binärfilerna om du är osäker.
    
2. Om du uppgraderar från Microsoft Dynamics AX 2012 installerar du följande X++-snabbkorrigeringar för appar i målmiljön innan du kör datauppgraderingen:
    - KB 4033183 - Uppgradering av Dynamics AX 2012 R2 eller Dynamics AX 2012 R3 Pre-CU8 som inte berör butik misslyckas med "Objektet hittades" inte för dbo.RETAILTILLLAYOUTZONE.
    - KB 4040692 - Uppgraderingen av Dynamics AX 2012 R3 till Microsoft Dynamics 365 for Operations 7.2 misslyckas vid dupliceringsindex RetailSalesLine vid SalesLineIdx.
    - KB 4035490 - Prestandaproblem med fältuppgraderingsskriptet för GeneralJournalAccountEntry MainAccount.


Följ dessa steg när du kör verktyget för omreservering av miljön.

1. Välj **Distribuerbart programpaket** i biblioteket med gemensamma tillgångar.
2. Hämta verktyget för omreservering av miljön.
3. Välj **Distribuerbart programpaket** i tillgångsbiblioteket för ditt projekt.
4. Skapa ett nytt paket genom att välja **Nytt**.
5. Ange ett namn och en beskrivning för paketet. Du kan använda **Verktyget för omreservering av miljön** som paketnamn.
6. Ladda upp paketet som du hämtade tidigare.
7. På sidan **Miljöinformation** för målmiljön väljer du **Underhåll** > **Tillämpa uppdateringar.**
8. Välj det verktyg för omreservering av miljön som du laddade upp tidigare och välj **Tillämpa** för att installera paketet.
9. Övervaka paketdistributionens förlopp. 

Mer information om hur du installerar ett distribuerbart paket finns i [Tillämpa ett distribuerbart paket](../deployment/create-apply-deployable-package.md). Mer information om hur du installerar ett distribuerbart paket manuellt finns i [Installera ett distribuerbart paket](../deployment/install-deployable-package.md).
