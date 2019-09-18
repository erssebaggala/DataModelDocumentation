{::nomarkdown}
<style>

.link {
  fill: none;
  stroke: rgba(100, 100, 100, .3);
  stroke-width: 1.5px;
}

#licensing {
  fill: green;
}

.link.licensing {
  stroke: green;
}

.link.resolved {
  stroke-dasharray: 0,2 1;
}

circle {
  fill: #F00;
  stroke: #ccc;
  stroke-width: 1.5px;
}

text {
  font: 20px sans-serif;
  pointer-events: none;
  text-shadow: 0 1px 0 #fff, 1px 0 0 #fff, 0 -1px 0 #fff, -1px 0 0 #fff;
}



</style>
<body>
<script src="https://d3js.org/d3.v3.min.js"></script>
<script>


var links = [
    {
        "source": "SalesLead",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "SalesLeadStateType",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "SalesLeadPriorityType",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "MarketingCampaignRef",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "MarketSegmentRef",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "ChannelRef",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "ProductOfferingRef",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "ProductSpecificationRef",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "CategoryRef",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "SalesOpportunityRef",
        "type": "suit"
    },
    {
        "source": "SalesLead",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "SalesOpportunityRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "MarketingCampaignRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "MarketSegmentRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AgreementSpecificationRelationship",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "AgreementSpecificationRelationship",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "SLAViolationRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrganizationChildRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrganizationChildRelationship",
        "target": "OrganizationRef",
        "type": "suit"
    },
    {
        "source": "AgreementAttachment",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RelatedPartyRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RoleType",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SLAViolation",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SLAViolation",
        "target": "Violation",
        "type": "suit"
    },
    {
        "source": "SLAViolation",
        "target": "SLARef",
        "type": "suit"
    },
    {
        "source": "AgreementSpecCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AgreementSpecCharacteristic",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "AgreementSpecificationRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "OtherNameOrganization",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OtherNameOrganization",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "PartnershipSpecificationRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "PartyCreditProfile",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PartyCreditProfile",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Partner",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Partner",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Partner",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "TaxExemptionCertificate",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TaxExemptionCertificate",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "TaxExemptionCertificate",
        "target": "AttachmentRefOrValue",
        "type": "suit"
    },
    {
        "source": "PartyRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "IndividualIdentification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "IndividualIdentification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "IndividualIdentification",
        "target": "AttachmentRefOrValue",
        "type": "suit"
    },
    {
        "source": "Party",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SettlementAccount",
        "target": "PartyAccount",
        "type": "suit"
    },
    {
        "source": "Agreement",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Agreement",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Agreement",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Agreement",
        "target": "AgreementSpecificationRef",
        "type": "suit"
    },
    {
        "source": "AccountDirectDetails",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AccountDirectDetails",
        "target": "AccountRef",
        "type": "suit"
    },
    {
        "source": "Individual",
        "target": "Party",
        "type": "suit"
    },
    {
        "source": "Individual",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Individual",
        "target": "IndividualStateType",
        "type": "suit"
    },
    {
        "source": "AccountRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AccountRelationship",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "AccountRelationship",
        "target": "AccountRef",
        "type": "suit"
    },
    {
        "source": "PartyRole",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PartyRole",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "PartyRole",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "Partnership",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Partnership",
        "target": "PartnershipSpecificationRef",
        "type": "suit"
    },
    {
        "source": "Violation",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Violation",
        "target": "AttachmentRef",
        "type": "suit"
    },
    {
        "source": "Violation",
        "target": "RuleRef",
        "type": "suit"
    },
    {
        "source": "AgreementTermOrCondition",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AgreementTermOrCondition",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "PartnershipSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "LanguageAbility",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "LanguageAbility",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "PartnershipTypeRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrganizationParentRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrganizationParentRelationship",
        "target": "OrganizationRef",
        "type": "suit"
    },
    {
        "source": "AgreementRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "AgreementItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PartyAccount",
        "target": "Account",
        "type": "suit"
    },
    {
        "source": "PartyAccount",
        "target": "BillStructure",
        "type": "suit"
    },
    {
        "source": "PartyAccount",
        "target": "FinancialAccountRef",
        "type": "suit"
    },
    {
        "source": "PartyAccount",
        "target": "PaymentMethodRef",
        "type": "suit"
    },
    {
        "source": "PartyBill",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PartyBill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "PartyBill",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "PartyBill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "PartyBill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "PartyBill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "PartyBill",
        "target": "BillingAccountRef",
        "type": "suit"
    },
    {
        "source": "PartyBill",
        "target": "PaymentMethodRef",
        "type": "suit"
    },
    {
        "source": "PartyBill",
        "target": "FinancialAccountRef",
        "type": "suit"
    },
    {
        "source": "AccountDirectMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AccountDirectMethod",
        "target": "AccountRef",
        "type": "suit"
    },
    {
        "source": "AccountDirectMethod",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "AccountDirectMethod",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "PartyRoleRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AccountBalanceRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AccountBalanceRef",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "RelatedPartyRefOrValue",
        "target": "Party",
        "type": "suit"
    },
    {
        "source": "RelatedPartyRefOrValue",
        "target": "PartyRef",
        "type": "suit"
    },
    {
        "source": "BankAccountDebitMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BankAccountDebitMethod",
        "target": "BankAccountDebitDetails",
        "type": "suit"
    },
    {
        "source": "BankAccountDebitMethod",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "BankAccountDebitMethod",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "AgreementItemRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "Account",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Account",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "Organization",
        "target": "Party",
        "type": "suit"
    },
    {
        "source": "Organization",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Organization",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Organization",
        "target": "OrganizationStateType",
        "type": "suit"
    },
    {
        "source": "Organization",
        "target": "OrganizationParentRelationship",
        "type": "suit"
    },
    {
        "source": "RuleRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BankAccount",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PartyOrPartyRoleRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PartyAccountRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TemplateRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "FinancialAccountRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "FinancialAccountRef",
        "target": "AccountBalance",
        "type": "suit"
    },
    {
        "source": "OrganizationIdentification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrganizationIdentification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "OrganizationIdentification",
        "target": "AttachmentRefOrValue",
        "type": "suit"
    },
    {
        "source": "OtherNameIndividual",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OtherNameIndividual",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "RoleSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PartnershipRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "OrganizationRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "SLARef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AgreementSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AgreementSpecification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "AgreementSpecification",
        "target": "CategoryRef",
        "type": "suit"
    },
    {
        "source": "FinancialAccount",
        "target": "Account",
        "type": "suit"
    },
    {
        "source": "BankAccountDebitDetails",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SLA",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SLA",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "SLA",
        "target": "TemplateRef",
        "type": "suit"
    },
    {
        "source": "PartnershipSpecificationRoleRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "AgreementAuthorization",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OtherName",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OtherName",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "AgreementSpecCharacteristicValue",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AgreementSpecCharacteristicValue",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "AgreementSpecCharacteristicValue",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "AccountBalance",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AccountBalance",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "AccountBalance",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "AccountRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AccountTaxExemption",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AccountTaxExemption",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "RoleTypeRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Rule",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "IssuerRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Contact",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Contact",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Contact",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "Skill",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Skill",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "BankAccountTransferDetails",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RelatedParty",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "PartnershipType",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BankAccountTransferMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BankAccountTransferMethod",
        "target": "BankAccountTransferDetails",
        "type": "suit"
    },
    {
        "source": "BankAccountTransferMethod",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "BankAccountTransferMethod",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "AlternateProduct",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AlternateProduct",
        "target": "ProductSpecificationRef",
        "type": "suit"
    },
    {
        "source": "UsageConsumptionReportRequestIn",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "UsageConsumptionReportRequestIn",
        "target": "NetworkProductRef",
        "type": "suit"
    },
    {
        "source": "UsageConsumptionReportRequestIn",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Category",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Category",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "LoyaltyAccount",
        "target": "LoyaltyProgramProductRef",
        "type": "suit"
    },
    {
        "source": "ProductOfferingTerm",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOfferingTerm",
        "target": "Quantity",
        "type": "suit"
    },
    {
        "source": "ProductOfferingTerm",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "CancelOrder",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CancelOrder",
        "target": "TaskStateType",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualification",
        "target": "ChannelRef",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualification",
        "target": "CategoryRef",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualification",
        "target": "TaskStateType",
        "type": "suit"
    },
    {
        "source": "BundledProductOfferingRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "LoyaltyAction",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "LoyaltyAction",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "LoyaltyAction",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "ProductOfferingPriceRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "ProductSpecCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecCharacteristic",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "QualificationItemRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Product",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Product",
        "target": "BillingAccountRef",
        "type": "suit"
    },
    {
        "source": "Product",
        "target": "ProductOfferingRef",
        "type": "suit"
    },
    {
        "source": "Product",
        "target": "ProductSpecificationRef",
        "type": "suit"
    },
    {
        "source": "Product",
        "target": "ProductStatusType",
        "type": "suit"
    },
    {
        "source": "ProductCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Promotion",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Promotion",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "UsageSpecCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationCharacteristicValueUse",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationCharacteristicValueUse",
        "target": "ProductSpecificationRef",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualificationItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualificationItem",
        "target": "ProductActionType",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualificationItem",
        "target": "TaskStateType",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualificationItem",
        "target": "ProductRefOrValue",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualificationItem",
        "target": "ProductOfferingRef",
        "type": "suit"
    },
    {
        "source": "ProductOffering",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOffering",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductOffering",
        "target": "SLARef",
        "type": "suit"
    },
    {
        "source": "ProductOffering",
        "target": "ProductSpecificationRef",
        "type": "suit"
    },
    {
        "source": "ProductOffering",
        "target": "ServiceCandidateRef",
        "type": "suit"
    },
    {
        "source": "ProductOffering",
        "target": "ResourceCandidateRef",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualificationItemRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualificationItemRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "CategoryRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "UsageConsumptionReportRequest",
        "target": "NetworkProductRef",
        "type": "suit"
    },
    {
        "source": "UsageConsumptionReportRequest",
        "target": "UsageConsumptionReportRef",
        "type": "suit"
    },
    {
        "source": "UsageConsumptionReportRequest",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "RelatedProductOrderItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "UsageVolumeProduct",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PromotionAction",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CancelProductOrder",
        "target": "CancelOrder",
        "type": "suit"
    },
    {
        "source": "CancelProductOrder",
        "target": "ProductOrderRef",
        "type": "suit"
    },
    {
        "source": "LoyaltyBalance",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "LoyaltyBalance",
        "target": "LoyaltyProgramMemberRef",
        "type": "suit"
    },
    {
        "source": "LoyaltyBalance",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "LoyaltyEvent",
        "target": "LoyaltyProgramProductRef",
        "type": "suit"
    },
    {
        "source": "LoyaltyEvent",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "ProductPrice",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductPrice",
        "target": "ProductOfferingPriceRef",
        "type": "suit"
    },
    {
        "source": "ProductPrice",
        "target": "BillingAccountRef",
        "type": "suit"
    },
    {
        "source": "ProductPrice",
        "target": "Price",
        "type": "suit"
    },
    {
        "source": "PromotionCriteriaGroup",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BundledProductSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecCharacteristicValue",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecCharacteristicValue",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductInventoryRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductInventoryRelationship",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "PromotionCriteria",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RecommendationItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RecommendationItem",
        "target": "ProductOfferingRef",
        "type": "suit"
    },
    {
        "source": "ProductOfferingRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "ProductRefOrValue",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "ProductRefOrValue",
        "target": "Product",
        "type": "suit"
    },
    {
        "source": "PriceAlteration",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PriceAlteration",
        "target": "ProductOfferingPriceRef",
        "type": "suit"
    },
    {
        "source": "PriceAlteration",
        "target": "Price",
        "type": "suit"
    },
    {
        "source": "ConsumptionSummary",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ConsumptionSummary",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ConsumptionSummary",
        "target": "NetworkProductRef",
        "type": "suit"
    },
    {
        "source": "ConsumptionSummary",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "ConsumptionSummary",
        "target": "Quantity",
        "type": "suit"
    },
    {
        "source": "ProductTerm",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductTerm",
        "target": "Quantity",
        "type": "suit"
    },
    {
        "source": "ProductTerm",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductOfferingPrice",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOfferingPrice",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductOfferingPrice",
        "target": "Quantity",
        "type": "suit"
    },
    {
        "source": "ProductOfferingPrice",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "Recommendation",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Recommendation",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Recommendation",
        "target": "ProductOrderRef",
        "type": "suit"
    },
    {
        "source": "Recommendation",
        "target": "GeographicLocationRef",
        "type": "suit"
    },
    {
        "source": "Recommendation",
        "target": "ChannelRef",
        "type": "suit"
    },
    {
        "source": "Recommendation",
        "target": "CategoryRef",
        "type": "suit"
    },
    {
        "source": "Recommendation",
        "target": "ShoppingCartRef",
        "type": "suit"
    },
    {
        "source": "Recommendation",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "ProductRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductRelationship",
        "target": "ProductRefOrValue",
        "type": "suit"
    },
    {
        "source": "ProductRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationCharacteristicValue",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationCharacteristicValue",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationCharacteristicValue",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationCharacteristicRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationCharacteristicRelationship",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "UsageCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BundledProductOfferingPriceRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductSpecification",
        "target": "TargetProductSchema",
        "type": "suit"
    },
    {
        "source": "ProductRequest",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductRequest",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "ProductRequest",
        "target": "ProductOfferingRef",
        "type": "suit"
    },
    {
        "source": "ProductRequest",
        "target": "ProductSpecificationRef",
        "type": "suit"
    },
    {
        "source": "NetworkProduct",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AlternateProductOfferingProposal",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AlternateProductOfferingProposal",
        "target": "ProductRefOrValue",
        "type": "suit"
    },
    {
        "source": "AlternateProductOfferingProposal",
        "target": "ProductOfferingRef",
        "type": "suit"
    },
    {
        "source": "LoyaltyProgramProductSpec",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "UsageConsumptionReport",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "UsageConsumptionReport",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "ProductSpecCharRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecCharRelationship",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "BaseProductRefOrValue",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BaseProductRefOrValue",
        "target": "ProductSpecificationRef",
        "type": "suit"
    },
    {
        "source": "LoyaltyProgramProductRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "UsageSpecificationRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "LoyaltyProgramMember",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "LoyaltyProgramMember",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "BundledProductOffering",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BundledProductOffering",
        "target": "BundledProductOfferingOption",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationCharacteristic",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationRelationship",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "LoyaltyExecutionPoint",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "LoyaltyExecutionPoint",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "LoyaltyExecutionPoint",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "EligibilityUnavailabilityReason",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "QuoteTerm",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "QuoteTerm",
        "target": "Quantity",
        "type": "suit"
    },
    {
        "source": "UsageVolumeBalance",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "UsageVolumeBalance",
        "target": "Quantity",
        "type": "suit"
    },
    {
        "source": "UsageVolumeBalance",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationSchemaRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "UsageSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "UsageSpecification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductOfferingPriceRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "LoyaltyProgramMemberRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PromotionPattern",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PromotionPattern",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "ProductSpecificationRef",
        "target": "TargetProductSchema",
        "type": "suit"
    },
    {
        "source": "BundledProductOfferingOption",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PricingLogicAlgorithm",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PricingLogicAlgorithm",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "UsageConsumptionReportRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Usage",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Usage",
        "target": "UsageSpecificationRef",
        "type": "suit"
    },
    {
        "source": "ProductRestriction",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductRestriction",
        "target": "ProductSpecificationRef",
        "type": "suit"
    },
    {
        "source": "UsageVolumeProductRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Catalog",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Catalog",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "LoyaltyProgramProduct",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "LoyaltyProgramProduct",
        "target": "LoyaltyProgramProductSpecRef",
        "type": "suit"
    },
    {
        "source": "LoyaltyProgramProduct",
        "target": "LoyaltyAccountRef",
        "type": "suit"
    },
    {
        "source": "LoyaltyProgramProduct",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "UsageSpecCharacteristicValue",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "NetworkProductRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOfferingQualificationRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "EntityCategory",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntityCategory",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ChangeRequestSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ChangeRequestSpecification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "RelatedPlace",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntityCatalogItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntityCatalogItem",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "DocumentCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Association",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Association",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Association",
        "target": "AssociationSpecRef",
        "type": "suit"
    },
    {
        "source": "Association",
        "target": "AssociationRole",
        "type": "suit"
    },
    {
        "source": "AlternateGeographicAddress",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AlternateGeographicAddress",
        "target": "GeographicLocation",
        "type": "suit"
    },
    {
        "source": "RelatedGeographicAddressRefOrValue",
        "target": "RelatedPlaceRefOrValue",
        "type": "suit"
    },
    {
        "source": "Money",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "QualificationRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "DocumentRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "GeographicSubAddress",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AssociationRoleSpec",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "LocationCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "GeographicSiteRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "StatusChange",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Street",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntitySpecRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntitySpecRelationship",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "EntitySpecRelationship",
        "target": "AssociationSpecRef",
        "type": "suit"
    },
    {
        "source": "RelatedPlaceRefOrValue",
        "target": "PlaceRef",
        "type": "suit"
    },
    {
        "source": "RelatedPlaceRefOrValue",
        "target": "Place",
        "type": "suit"
    },
    {
        "source": "Address",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Address",
        "target": "SubAddress",
        "type": "suit"
    },
    {
        "source": "TicketRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TicketRelationship",
        "target": "TroubleTicketRef",
        "type": "suit"
    },
    {
        "source": "Characteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Characteristic",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "EntitySpecificationRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SpecCharacteristicValue",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SpecCharacteristicValue",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "SpecCharacteristicValue",
        "target": "Object",
        "type": "suit"
    },
    {
        "source": "BusinessInteraction",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProcessFlowRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "ProcessFlowRef",
        "target": "ProcessFlowStateType",
        "type": "suit"
    },
    {
        "source": "CalendarPeriod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RelatedChangeRequestRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Resolution",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ExportJob",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ExportJob",
        "target": "JobStateType",
        "type": "suit"
    },
    {
        "source": "GeographicAddressValidation",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "GeographicAddressValidation",
        "target": "GeographicAddress",
        "type": "suit"
    },
    {
        "source": "AssociationSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AssociationSpecification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "AssociationSpecification",
        "target": "AssociationRoleSpec",
        "type": "suit"
    },
    {
        "source": "Area",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "GeographicAddress",
        "target": "Place",
        "type": "suit"
    },
    {
        "source": "GeographicAddress",
        "target": "GeographicLocation",
        "type": "suit"
    },
    {
        "source": "Place",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "GeographicPoint",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CommunicationMessage",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CommunicationMessage",
        "target": "Sender",
        "type": "suit"
    },
    {
        "source": "Ticket",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ImpactEntityRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntityCatalog",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntityCatalog",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ImportJob",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ImportJob",
        "target": "JobStateType",
        "type": "suit"
    },
    {
        "source": "ProcessFlow",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProcessFlow",
        "target": "ProcessFlowStateType",
        "type": "suit"
    },
    {
        "source": "GeographicLocationRef",
        "target": "PlaceRef",
        "type": "suit"
    },
    {
        "source": "FileDocument",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AssociationRole",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SiteRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SiteRelationship",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "TaskFlowRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntitySpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntitySpecification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "EntitySpecification",
        "target": "EntitySchemaRef",
        "type": "suit"
    },
    {
        "source": "AddressRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "MediumCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RelatedObject",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Hub",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Monitor",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Monitor",
        "target": "Request",
        "type": "suit"
    },
    {
        "source": "Monitor",
        "target": "Response",
        "type": "suit"
    },
    {
        "source": "ReceiverRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TroubleTicket",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TroubleTicket",
        "target": "ChannelRef",
        "type": "suit"
    },
    {
        "source": "TroubleTicket",
        "target": "TroubleTicketStatusType",
        "type": "suit"
    },
    {
        "source": "GeographicLocation",
        "target": "Place",
        "type": "suit"
    },
    {
        "source": "Incident",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "DocumentRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "DocumentRelationship",
        "target": "DocumentRef",
        "type": "suit"
    },
    {
        "source": "Sender",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Sender",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "EntitySchemaRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Event",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Event",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "TaxDefinition",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AttachmentRefOrValue",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AttachmentRefOrValue",
        "target": "ContentType",
        "type": "suit"
    },
    {
        "source": "AttachmentRefOrValue",
        "target": "Quantity",
        "type": "suit"
    },
    {
        "source": "AttachmentRefOrValue",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "EntityAttachment",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntityAttachment",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Document",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Document",
        "target": "DocumentSpecification",
        "type": "suit"
    },
    {
        "source": "Document",
        "target": "RelatedObject",
        "type": "suit"
    },
    {
        "source": "AttachmentRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "Record",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RelatedEntity",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "SubAddress",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Topic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ContactMedium",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ContactMedium",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ContactMedium",
        "target": "MediumCharacteristic",
        "type": "suit"
    },
    {
        "source": "TaskFlow",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TaskFlow",
        "target": "TaskFlowStateType",
        "type": "suit"
    },
    {
        "source": "Channel",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "DocumentAttachment",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "DocumentAttachment",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Value",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "HourPeriod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Object",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "GeographicAddressRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Task",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RetrieveLocationRelation",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RetrieveLocationRelation",
        "target": "GeographicLocationRef",
        "type": "suit"
    },
    {
        "source": "RelatedChannel",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "PlaceRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "CommunicationRequestCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RatedProductUsage",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ChannelRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "AssociationSpecRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ChangeRequestCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SpecCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SpecCharacteristic",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ExternalReference",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Receiver",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Receiver",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "TaskFlowRelationship",
        "target": "TaskFlowRef",
        "type": "suit"
    },
    {
        "source": "TroubleTicketRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "EventRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BaseEvent",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "EntityCatalogItemRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ConstraintRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "WorkLog",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BasePlusEvent",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TroubleTicketRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TroubleTicketRelationship",
        "target": "TroubleTicketRef",
        "type": "suit"
    },
    {
        "source": "EntityRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "GeographicSite",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "GeographicSite",
        "target": "GeographicLocation",
        "type": "suit"
    },
    {
        "source": "GeographicSite",
        "target": "GeographicAddress",
        "type": "suit"
    },
    {
        "source": "RetrieveGeographicLocation",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RetrieveGeographicLocation",
        "target": "GeographicLocation",
        "type": "suit"
    },
    {
        "source": "RetrieveGeographicLocation",
        "target": "Object",
        "type": "suit"
    },
    {
        "source": "ChangeRequestRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Attachment",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Attachment",
        "target": "Quantity",
        "type": "suit"
    },
    {
        "source": "Attachment",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "TargetEntityRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "StreetSegment",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "StreetSegment",
        "target": "AddressRef",
        "type": "suit"
    },
    {
        "source": "ChangeRequest",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ChangeRequest",
        "target": "WorkLog",
        "type": "suit"
    },
    {
        "source": "ChangeRequest",
        "target": "ChangeRequestSpecification",
        "type": "suit"
    },
    {
        "source": "ChangeRequest",
        "target": "Resolution",
        "type": "suit"
    },
    {
        "source": "ChangeRequest",
        "target": "GeographicAddressRef",
        "type": "suit"
    },
    {
        "source": "TimePeriod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SpecCharRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SpecCharRelationship",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Note",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RelatedGeographicLocationRefOrValue",
        "target": "RelatedPlaceRefOrValue",
        "type": "suit"
    },
    {
        "source": "RelatedEntityRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "DocumentSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CalendarEventRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "Notification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Error",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceOrderItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceOrderItem",
        "target": "ResourceSpecificationRef",
        "type": "suit"
    },
    {
        "source": "ResourceOrderItemRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceOrderItemRelationship",
        "target": "ResourceOrderItemRef",
        "type": "suit"
    },
    {
        "source": "ResourceRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceRelationship",
        "target": "ResourceRef",
        "type": "suit"
    },
    {
        "source": "SupportingResource",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Resource",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Resource",
        "target": "Place",
        "type": "suit"
    },
    {
        "source": "ResourceOrderItemRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceCandidateRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceOrderRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "RealizingResourceRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "PhysicalResource",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PhysicalResource",
        "target": "Place",
        "type": "suit"
    },
    {
        "source": "ResourceOrder",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceOrderRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceOrderRelationship",
        "target": "ResourceOrderRef",
        "type": "suit"
    },
    {
        "source": "ResourceOrderRelationship",
        "target": "ServiceOrderRef",
        "type": "suit"
    },
    {
        "source": "LogicalResource",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "LogicalResource",
        "target": "Place",
        "type": "suit"
    },
    {
        "source": "ResourceRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "ResourceSpecificationRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceAlarmRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ResourceAlarmRef",
        "target": "ChangeRequestRef",
        "type": "suit"
    },
    {
        "source": "ShoppingCartRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Disability",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Disability",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Bucket",
        "target": "BucketBalance",
        "type": "suit"
    },
    {
        "source": "Quote",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Quote",
        "target": "QuoteStateType",
        "type": "suit"
    },
    {
        "source": "Quote",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "CartTerm",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CartTerm",
        "target": "Quantity",
        "type": "suit"
    },
    {
        "source": "SettlementMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SettlementNoteAdvice",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SettlementNoteAdvice",
        "target": "SettlementMethod",
        "type": "suit"
    },
    {
        "source": "SettlementNoteAdvice",
        "target": "SettlementNoteImage",
        "type": "suit"
    },
    {
        "source": "SettlementNoteAdvice",
        "target": "PartyRef",
        "type": "suit"
    },
    {
        "source": "SettlementNoteAdvice",
        "target": "PartyRef",
        "type": "suit"
    },
    {
        "source": "BillingAccount",
        "target": "PartyAccount",
        "type": "suit"
    },
    {
        "source": "ProductOrderRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "Appointment",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Appointment",
        "target": "CalendarEventRef",
        "type": "suit"
    },
    {
        "source": "Appointment",
        "target": "RelatedPlaceRefOrValue",
        "type": "suit"
    },
    {
        "source": "Appointment",
        "target": "AppointmentStateType",
        "type": "suit"
    },
    {
        "source": "Appointment",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "BillRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "QueryProductRecommendation",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "QueryProductRecommendation",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "QueryProductRecommendation",
        "target": "ProductOrderRef",
        "type": "suit"
    },
    {
        "source": "QueryProductRecommendation",
        "target": "RelatedPlaceRefOrValue",
        "type": "suit"
    },
    {
        "source": "QueryProductRecommendation",
        "target": "ChannelRef",
        "type": "suit"
    },
    {
        "source": "QueryProductRecommendation",
        "target": "CategoryRef",
        "type": "suit"
    },
    {
        "source": "QueryProductRecommendation",
        "target": "ShoppingCartRef",
        "type": "suit"
    },
    {
        "source": "QueryProductRecommendation",
        "target": "RelatedPartyRef",
        "type": "suit"
    },
    {
        "source": "QueryProductRecommendation",
        "target": "TaskStateType",
        "type": "suit"
    },
    {
        "source": "BankCardDetails",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceTransferRequest",
        "target": "BalanceTransferBody",
        "type": "suit"
    },
    {
        "source": "BalanceTransferRequest",
        "target": "BucketBalanceRef",
        "type": "suit"
    },
    {
        "source": "BalanceTransferRequest",
        "target": "PartyAccountRef",
        "type": "suit"
    },
    {
        "source": "BalanceTransferRequest",
        "target": "RelatedPartyRef",
        "type": "suit"
    },
    {
        "source": "BalanceTransferRequest",
        "target": "RelatedPartyRef",
        "type": "suit"
    },
    {
        "source": "BalanceTransferRequest",
        "target": "QuantityType",
        "type": "suit"
    },
    {
        "source": "QuoteRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "CashMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CashMethod",
        "target": "CashDetails",
        "type": "suit"
    },
    {
        "source": "CashMethod",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "CashMethod",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "CashDetails",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrderItemRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BillPresentationMedia",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOrder",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOrder",
        "target": "BillingAccountRef",
        "type": "suit"
    },
    {
        "source": "ProductOrder",
        "target": "ProductOrderStateType",
        "type": "suit"
    },
    {
        "source": "BalanceReserve",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceReserve",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "BalanceReserve",
        "target": "PartyAccountRef",
        "type": "suit"
    },
    {
        "source": "BalanceReserve",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "BalanceReserve",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "BalanceReserve",
        "target": "PartyAccountRef",
        "type": "suit"
    },
    {
        "source": "BalanceTopupBody",
        "target": "QuantityType",
        "type": "suit"
    },
    {
        "source": "BalanceTopupBody",
        "target": "ChannelRef",
        "type": "suit"
    },
    {
        "source": "BalanceTopupBody",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "BillingCycleSpecificationRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceDeductRollback",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceDeductRollback",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "BalanceDeductRollback",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "BalanceDeductRollback",
        "target": "PartyAccountRef",
        "type": "suit"
    },
    {
        "source": "BalanceDeductRollback",
        "target": "BalanceDeductRef",
        "type": "suit"
    },
    {
        "source": "BalanceDeductRollback",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "AppliedCustomerBillingRate",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AppliedCustomerBillingRate",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "AppliedCustomerBillingRate",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "AppliedCustomerBillingRate",
        "target": "BillRef",
        "type": "suit"
    },
    {
        "source": "SettlementNoteItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SettlementNoteItem",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ShoppingCart",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ShoppingCart",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "SearchTimeSlot",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "SearchTimeSlot",
        "target": "SearchTimeSlotStateType",
        "type": "suit"
    },
    {
        "source": "SearchTimeSlot",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "SearchTimeSlot",
        "target": "RelatedPlaceRefOrValue",
        "type": "suit"
    },
    {
        "source": "BalanceUnreserve",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceUnreserve",
        "target": "BalanceReserveRef",
        "type": "suit"
    },
    {
        "source": "BalanceUnreserve",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "BalanceUnreserve",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "BalanceUnreserve",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "QuoteItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "QuoteItem",
        "target": "ProductRefOrValue",
        "type": "suit"
    },
    {
        "source": "QuoteItem",
        "target": "ProductOfferingRef",
        "type": "suit"
    },
    {
        "source": "QuoteItem",
        "target": "ProductOfferingQualificationItemRef",
        "type": "suit"
    },
    {
        "source": "Bill",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Bill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "Bill",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Bill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "Bill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "Bill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "Bill",
        "target": "BillingAccountRef",
        "type": "suit"
    },
    {
        "source": "Bill",
        "target": "PaymentMethodRef",
        "type": "suit"
    },
    {
        "source": "Bill",
        "target": "FinancialAccountRef",
        "type": "suit"
    },
    {
        "source": "QuoteItemRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BillFormat",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceTransferBody",
        "target": "QuantityType",
        "type": "suit"
    },
    {
        "source": "BalanceTransferBody",
        "target": "ChannelRef",
        "type": "suit"
    },
    {
        "source": "BalanceTransferBody",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "BalanceDeductRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOrderItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProductOrderItem",
        "target": "OrderItemActionType",
        "type": "suit"
    },
    {
        "source": "ProductOrderItem",
        "target": "AppointmentRef",
        "type": "suit"
    },
    {
        "source": "ProductOrderItem",
        "target": "BillingAccountRef",
        "type": "suit"
    },
    {
        "source": "ProductOrderItem",
        "target": "ProductRefOrValue",
        "type": "suit"
    },
    {
        "source": "ProductOrderItem",
        "target": "ProductOfferingRef",
        "type": "suit"
    },
    {
        "source": "ProductOrderItem",
        "target": "ProductOfferingQualificationItemRef",
        "type": "suit"
    },
    {
        "source": "ProductOrderItem",
        "target": "QuoteItemRef",
        "type": "suit"
    },
    {
        "source": "ProductOrderItem",
        "target": "ProductOrderItemStateType",
        "type": "suit"
    },
    {
        "source": "Customer",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Customer",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Customer",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "CustomerBill",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CustomerBill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "CustomerBill",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "CustomerBill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "CustomerBill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "CustomerBill",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "CustomerBill",
        "target": "BillingAccountRef",
        "type": "suit"
    },
    {
        "source": "CustomerBill",
        "target": "PaymentMethodRef",
        "type": "suit"
    },
    {
        "source": "CustomerBill",
        "target": "FinancialAccountRef",
        "type": "suit"
    },
    {
        "source": "DigitalWalletMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "DigitalWalletMethod",
        "target": "DigitalWalletDetails",
        "type": "suit"
    },
    {
        "source": "DigitalWalletMethod",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "DigitalWalletMethod",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "BillingAccountRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BillFormatRefOrValue",
        "target": "BillFormatRef",
        "type": "suit"
    },
    {
        "source": "BillFormatRefOrValue",
        "target": "BillFormat",
        "type": "suit"
    },
    {
        "source": "AppliedBillingRate",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AppliedBillingRate",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "AppliedBillingRate",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "AppliedBillingRate",
        "target": "BillRef",
        "type": "suit"
    },
    {
        "source": "QuotePrice",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "QuotePrice",
        "target": "ProductOfferingPriceRef",
        "type": "suit"
    },
    {
        "source": "QuotePrice",
        "target": "Price",
        "type": "suit"
    },
    {
        "source": "BillPresentationMediaRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "VoucherDetails",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "QuoteItemRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "BalanceAdjustmentRequest",
        "target": "BalanceAdjustmentBody",
        "type": "suit"
    },
    {
        "source": "BalanceAdjustmentRequest",
        "target": "BucketBalanceRef",
        "type": "suit"
    },
    {
        "source": "BalanceAdjustmentRequest",
        "target": "PartyAccountRef",
        "type": "suit"
    },
    {
        "source": "BalanceAdjustmentRequest",
        "target": "RelatedPartyRef",
        "type": "suit"
    },
    {
        "source": "BalanceAdjustmentRequest",
        "target": "TimePeriodType",
        "type": "suit"
    },
    {
        "source": "AppointmentRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AppliedPartyBillingRate",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AppliedPartyBillingRate",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "AppliedPartyBillingRate",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "AppliedPartyBillingRate",
        "target": "BillRef",
        "type": "suit"
    },
    {
        "source": "TaxItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TaxItem",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "PaymentRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "TimeSlot",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TimeSlot",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "TimeSlot",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "BillingCycleSpecificationRefOrValue",
        "target": "BillingCycleSpecificationRef",
        "type": "suit"
    },
    {
        "source": "BillingCycleSpecificationRefOrValue",
        "target": "BillingCycleSpecification",
        "type": "suit"
    },
    {
        "source": "PaymentMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PaymentMethod",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "PaymentMethod",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "BankCardMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BankCardMethod",
        "target": "BankCardDetails",
        "type": "suit"
    },
    {
        "source": "BankCardMethod",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "BankCardMethod",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "AppliedBillingTaxRate",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AppliedBillingTaxRate",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "OrderItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrderItem",
        "target": "AppointmentRef",
        "type": "suit"
    },
    {
        "source": "OrderItem",
        "target": "BillingAccountRef",
        "type": "suit"
    },
    {
        "source": "OrderItem",
        "target": "ProductOfferingRef",
        "type": "suit"
    },
    {
        "source": "OrderItem",
        "target": "Product",
        "type": "suit"
    },
    {
        "source": "TokenizedCardDetails",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CartItemRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AppliedBillingRateCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CartPrice",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CartPrice",
        "target": "ProductOfferingPriceRef",
        "type": "suit"
    },
    {
        "source": "CartPrice",
        "target": "Price",
        "type": "suit"
    },
    {
        "source": "PaymentPlan",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PaymentPlan",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "PaymentPlan",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "PaymentPlan",
        "target": "PaymentMethodRef",
        "type": "suit"
    },
    {
        "source": "PaymentMethodRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceReserveRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Authorization",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceAdjustmentBody",
        "target": "QuantityType",
        "type": "suit"
    },
    {
        "source": "BalanceAdjustmentBody",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "CheckMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CheckMethod",
        "target": "CheckDetails",
        "type": "suit"
    },
    {
        "source": "CheckMethod",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "CheckMethod",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "DigitalWalletDetails",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceTopupStatus",
        "target": "BalanceTopupStatusTypeModify",
        "type": "suit"
    },
    {
        "source": "CreditProfile",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CreditProfile",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "CartItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "CartItem",
        "target": "CartItemActionType",
        "type": "suit"
    },
    {
        "source": "CartItem",
        "target": "CartItemStatusType",
        "type": "suit"
    },
    {
        "source": "CartItem",
        "target": "ProductRefOrValue",
        "type": "suit"
    },
    {
        "source": "CartItem",
        "target": "ProductOfferingRef",
        "type": "suit"
    },
    {
        "source": "CheckDetails",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BillStructure",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BillStructure",
        "target": "BillFormatRefOrValue",
        "type": "suit"
    },
    {
        "source": "BillStructure",
        "target": "BillingCycleSpecificationRefOrValue",
        "type": "suit"
    },
    {
        "source": "BillingCycleSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BillingCycleSpecification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "OrderPrice",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrderPrice",
        "target": "ProductOfferingPriceRef",
        "type": "suit"
    },
    {
        "source": "OrderPrice",
        "target": "BillingAccountRef",
        "type": "suit"
    },
    {
        "source": "OrderPrice",
        "target": "Price",
        "type": "suit"
    },
    {
        "source": "BalanceTopupRequest",
        "target": "BalanceTopupBody",
        "type": "suit"
    },
    {
        "source": "BalanceTopupRequest",
        "target": "BucketBalanceRef",
        "type": "suit"
    },
    {
        "source": "BalanceTopupRequest",
        "target": "PartyAccountRef",
        "type": "suit"
    },
    {
        "source": "BalanceTopupRequest",
        "target": "PaymentMethodRefOrValue",
        "type": "suit"
    },
    {
        "source": "BalanceTopupRequest",
        "target": "RelatedPartyRef",
        "type": "suit"
    },
    {
        "source": "BalanceTopupRequest",
        "target": "TimePeriodType",
        "type": "suit"
    },
    {
        "source": "PaymentMethodRefOrValue",
        "target": "RelatedPartyRef",
        "type": "suit"
    },
    {
        "source": "CartItemRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Price",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "Price",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "Price",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "VoucherMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "VoucherMethod",
        "target": "VoucherDetails",
        "type": "suit"
    },
    {
        "source": "VoucherMethod",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "VoucherMethod",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "BillFormatRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrderItemPrice",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrderItemPrice",
        "target": "ProductOfferingPriceRef",
        "type": "suit"
    },
    {
        "source": "OrderItemPrice",
        "target": "BillingAccountRef",
        "type": "suit"
    },
    {
        "source": "OrderItemPrice",
        "target": "Price",
        "type": "suit"
    },
    {
        "source": "TokenizedCardMethod",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TokenizedCardMethod",
        "target": "TokenizedCardDetails",
        "type": "suit"
    },
    {
        "source": "TokenizedCardMethod",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "TokenizedCardMethod",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "BillPresentationMediaRefOrValue",
        "target": "BillPresentationMediaRef",
        "type": "suit"
    },
    {
        "source": "BillPresentationMediaRefOrValue",
        "target": "BillPresentationMedia",
        "type": "suit"
    },
    {
        "source": "OrderTerm",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "OrderTerm",
        "target": "Quantity",
        "type": "suit"
    },
    {
        "source": "AccumulatedBalance",
        "target": "QuantityType",
        "type": "suit"
    },
    {
        "source": "PaymentItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "PaymentItem",
        "target": "Money",
        "type": "suit"
    },
    {
        "source": "PaymentItem",
        "target": "PaymentRef",
        "type": "suit"
    },
    {
        "source": "OrderRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceActivity",
        "target": "BalanceActionRequestRef",
        "type": "suit"
    },
    {
        "source": "BalanceActivity",
        "target": "QuantityType",
        "type": "suit"
    },
    {
        "source": "BalanceActivity",
        "target": "QuantityType",
        "type": "suit"
    },
    {
        "source": "BalanceActivity",
        "target": "QuantityType",
        "type": "suit"
    },
    {
        "source": "BalanceActivity",
        "target": "BucketBalanceRef",
        "type": "suit"
    },
    {
        "source": "BalanceActivity",
        "target": "PartyAccountRef",
        "type": "suit"
    },
    {
        "source": "BalanceActivity",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "SettlementNoteImage",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceDeduct",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BalanceDeduct",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "BalanceDeduct",
        "target": "ProductRef",
        "type": "suit"
    },
    {
        "source": "BalanceDeduct",
        "target": "BalanceReserveRef",
        "type": "suit"
    },
    {
        "source": "BalanceDeduct",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "BalanceDeduct",
        "target": "PartyAccountRef",
        "type": "suit"
    },
    {
        "source": "BucketBalance",
        "target": "PartyAccountRef",
        "type": "suit"
    },
    {
        "source": "BucketBalance",
        "target": "QuantityType",
        "type": "suit"
    },
    {
        "source": "BucketBalance",
        "target": "QuantityType",
        "type": "suit"
    },
    {
        "source": "BucketBalance",
        "target": "TimePeriodType",
        "type": "suit"
    },
    {
        "source": "BaseService",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "BaseService",
        "target": "ServiceStateType",
        "type": "suit"
    },
    {
        "source": "BaseService",
        "target": "ServiceSpecificationRef",
        "type": "suit"
    },
    {
        "source": "ServiceCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceCharacteristic",
        "target": "Value",
        "type": "suit"
    },
    {
        "source": "ServiceQualificationItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceQualificationItem",
        "target": "ServiceRestriction",
        "type": "suit"
    },
    {
        "source": "ServiceQualificationItem",
        "target": "ServiceCategoryRef",
        "type": "suit"
    },
    {
        "source": "MeasureThresholdRuleViolation",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "MeasureThresholdRuleViolation",
        "target": "Duration",
        "type": "suit"
    },
    {
        "source": "ServiceCategory",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceCategory",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceTestSpecificationRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ImpactPattern",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceOrder",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceOrder",
        "target": "ServiceOrderStateType",
        "type": "suit"
    },
    {
        "source": "ServiceOfferingQualificationRef",
        "target": "QualificationRef",
        "type": "suit"
    },
    {
        "source": "ServiceLevelSpecParameter",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceLevelSpecParameter",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceCandidateRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceOrderRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceLevelSpecificationRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceEligibilityUnavailabilityReason",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceProblem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceProblem",
        "target": "RelatedEntityRef",
        "type": "suit"
    },
    {
        "source": "ServiceProblem",
        "target": "ImpactPattern",
        "type": "suit"
    },
    {
        "source": "ServiceProblem",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "ServiceProblem",
        "target": "RelatedParty",
        "type": "suit"
    },
    {
        "source": "TestMeasure",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TestMeasure",
        "target": "Characteristic",
        "type": "suit"
    },
    {
        "source": "ProblemUnacknowledgement",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProblemUnacknowledgement",
        "target": "TrackingRecord",
        "type": "suit"
    },
    {
        "source": "ServiceCatalog",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceCatalog",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceSpecCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceSpecCharacteristic",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceOrderItemRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceTestCharacteristic",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AlternateServiceProposal",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AlternateServiceProposal",
        "target": "ServiceRestriction",
        "type": "suit"
    },
    {
        "source": "ServiceSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceSpecification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceSpecification",
        "target": "TargetServiceSchema",
        "type": "suit"
    },
    {
        "source": "ServiceProblemEventRecord",
        "target": "ServiceProblemRef",
        "type": "suit"
    },
    {
        "source": "ServiceProblemEventRecord",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "ServiceCategoryRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProblemUngroup",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProblemUngroup",
        "target": "ServiceProblemRef",
        "type": "suit"
    },
    {
        "source": "MetricDefMeasureConsequence",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "MetricDefMeasureConsequence",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceQualificationRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceSpecCharRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceSpecCharRelationship",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "Service",
        "target": "BaseService",
        "type": "suit"
    },
    {
        "source": "ServiceCandidate",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceCandidate",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceCandidate",
        "target": "ServiceSpecificationRef",
        "type": "suit"
    },
    {
        "source": "ServiceLevelObjective",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceLevelObjective",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceLevelObjective",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceLevelObjective",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceLevelObjective",
        "target": "ServiceLevelSpecParameter",
        "type": "suit"
    },
    {
        "source": "ServiceLevelObjectiveRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "AppliedConsequence",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceRef",
        "target": "EntityRef",
        "type": "suit"
    },
    {
        "source": "ServiceQualificationItemRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceTestSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceTestSpecification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceTestSpecification",
        "target": "ServiceSpecificationRef",
        "type": "suit"
    },
    {
        "source": "ServiceLevelSpecification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceLevelSpecification",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ProblemGroup",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProblemGroup",
        "target": "ServiceProblemRef",
        "type": "suit"
    },
    {
        "source": "ServiceLevelSpecConsequence",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceLevelSpecConsequence",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "TestMeasureDefinition",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "TestMeasureDefinition",
        "target": "Duration",
        "type": "suit"
    },
    {
        "source": "TestMeasureDefinition",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "SupportingService",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceSpecCharacteristicValue",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceSpecCharacteristicValue",
        "target": "Any",
        "type": "suit"
    },
    {
        "source": "ServiceSpecCharacteristicValue",
        "target": "TimePeriod",
        "type": "suit"
    },
    {
        "source": "ServiceProblemRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "MetricDefMeasureThresholdRule",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "MetricDefMeasureThresholdRule",
        "target": "Duration",
        "type": "suit"
    },
    {
        "source": "ProblemAcknowledgement",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ProblemAcknowledgement",
        "target": "TrackingRecord",
        "type": "suit"
    },
    {
        "source": "FirstAlert",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceRelationship",
        "target": "ServiceRef",
        "type": "suit"
    },
    {
        "source": "ServiceOrderRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceQualification",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceOrderItem",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceOrderItem",
        "target": "ServiceOrderActionType",
        "type": "suit"
    },
    {
        "source": "ServiceOrderItem",
        "target": "ServiceOrderStateType",
        "type": "suit"
    },
    {
        "source": "ServiceOrderItem",
        "target": "BaseService",
        "type": "suit"
    },
    {
        "source": "ServiceOrderItem",
        "target": "AppointmentRef",
        "type": "suit"
    },
    {
        "source": "TrackingRecord",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceTest",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceTest",
        "target": "ServiceRef",
        "type": "suit"
    },
    {
        "source": "ServiceTest",
        "target": "ServiceTestSpecificationRef",
        "type": "suit"
    },
    {
        "source": "ServiceSpecificationRef",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceSpecificationRef",
        "target": "TargetServiceSchema",
        "type": "suit"
    },
    {
        "source": "ServiceSpecRelationship",
        "target": "Entity",
        "type": "suit"
    },
    {
        "source": "ServiceSpecRelationship",
        "target": "TimePeriod",
        "type": "suit"
    }
];

var nodes = {};

// Compute the distinct nodes from the links.
links.forEach(function(link) {
  link.source = nodes[link.source] || (nodes[link.source] = {name: link.source});
  link.target = nodes[link.target] || (nodes[link.target] = {name: link.target});
});

var width = 10000,
    height = 7000;

var force = d3.layout.force()
    .nodes(d3.values(nodes))
    .links(links)
    .size([width, height])
    .linkDistance(600)
    .charge(-3000)
    .on("tick", tick)
    .start();

var svg = d3.select("body").append("svg")
    .attr("width", width)
    .attr("height", height);

// Per-type markers, as they don't inherit styles.
svg.append("defs").selectAll("marker")
    .data(["suit", "licensing", "resolved"])
  .enter().append("marker")
    .attr("id", function(d) { return d; })
    .attr("viewBox", "0 -5 10 10")
    .attr("refX", 15)
    .attr("refY", -1.5)
    .attr("markerWidth", 6)
    .attr("markerHeight", 6)
    .attr("orient", "auto")
  .append("path")
    .attr("d", "M0,-5L10,0L0,5");

var path = svg.append("g").selectAll("path")
    .data(force.links())
  .enter().append("path")
    .attr("class", function(d) { return "link " + d.type; })
    .attr("marker-end", function(d) { return "url(#" + d.type + ")"; });

var circle = svg.append("g").selectAll("circle")
    .data(force.nodes())
  .enter().append("circle")
    .attr("r", 6)
    .call(force.drag);

var text = svg.append("g").selectAll("text")
    .data(force.nodes())
  .enter().append("text")
    .attr("x", 8)
    .attr("y", ".31em")
    .text(function(d) { return d.name; });

// Use elliptical arc path segments to doubly-encode directionality.
function tick() {
  path.attr("d", linkArc);
  circle.attr("transform", transform);
  text.attr("transform", transform);
}

function linkArc(d) {
  var dx = d.target.x - d.source.x,
      dy = d.target.y - d.source.y,
      dr = Math.sqrt(dx * dx + dy * dy);
  return "M" + d.source.x + "," + d.source.y + "A" + dr + "," + dr + " 0 0,1 " + d.target.x + "," + d.target.y;
}

function transform(d) {
  return "translate(" + d.x + "," + d.y + ")";
}

</script>
{:/}