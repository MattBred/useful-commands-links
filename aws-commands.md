* Delete all log groups by a prefixed log name (in this example, "/aws/codebuild")
   ```bash
   LOG_PREFIX="/aws/codebuild"

   LOG_GROUPS=$(aws logs describe-log-groups --log-group-name-prefix "${LOG_PREFIX}" --query 'logGroups[*].[logGroupName]' --output=text)

   for GROUP in "${LOG_GROUPS}"; do aws logs delete-log-group --log-group-name "${GROUP}"; done
   ```
