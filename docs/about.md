    "| __API__ | PLACEHOLDER_API |",
    "| __API Key Parameter__ | " + "<br>".join([
        "PLACEHOLDER_PARAM",
        "Set `pParam.szChildID` to `global`.",
        "Set `pParam.szLoadIndex` to `0`.",
        "Set `pParam.szResourceType` to `global`.",
        f"Set `pParam.szDomain` to {domain_identifier}." if domain_identifier else "PLACEHOLDER_DOMAIN",
        f"Set `pParam.szIdentifier` to {function_identifier}." if function_identifier else "PLACEHOLDER_IDENTIFIER"
    ]) + " |",
    "| __Remark__ | PLACEHOLDER_REMARK |"