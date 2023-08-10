## API Report File for "@backstage/plugin-permission-node"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
import { AllOfCriteria } from '@backstage/plugin-permission-common';
import { AnyOfCriteria } from '@backstage/plugin-permission-common';
import { AuthorizePermissionRequest } from '@backstage/plugin-permission-common';
import { AuthorizePermissionResponse } from '@backstage/plugin-permission-common';
import { BackstageIdentityResponse } from '@backstage/plugin-auth-node';
import { ConditionalPolicyDecision } from '@backstage/plugin-permission-common';
import { Config } from '@backstage/config';
import { DefinitivePolicyDecision } from '@backstage/plugin-permission-common';
import { EvaluatorRequestOptions } from '@backstage/plugin-permission-common';
import express from 'express';
import { IdentifiedPermissionMessage } from '@backstage/plugin-permission-common';
import { NotCriteria } from '@backstage/plugin-permission-common';
import { Permission } from '@backstage/plugin-permission-common';
import { PermissionCondition } from '@backstage/plugin-permission-common';
import { PermissionCriteria } from '@backstage/plugin-permission-common';
import { PermissionEvaluator } from '@backstage/plugin-permission-common';
import { PermissionRuleParams } from '@backstage/plugin-permission-common';
import { PluginEndpointDiscovery } from '@backstage/backend-common';
import { PolicyDecision } from '@backstage/plugin-permission-common';
import { QueryPermissionRequest } from '@backstage/plugin-permission-common';
import { ResourcePermission } from '@backstage/plugin-permission-common';
import { TokenManager } from '@backstage/backend-common';
import { z } from 'zod';
import zodToJsonSchema from 'zod-to-json-schema';

// @public
export type ApplyConditionsRequest = {
  items: ApplyConditionsRequestEntry[];
};

// @public
export type ApplyConditionsRequestEntry = IdentifiedPermissionMessage<{
  resourceRef: string;
  resourceType: string;
  conditions: PermissionCriteria<PermissionCondition>;
}>;

// @public
export type ApplyConditionsResponse = {
  items: ApplyConditionsResponseEntry[];
};

// @public
export type ApplyConditionsResponseEntry =
  IdentifiedPermissionMessage<DefinitivePolicyDecision>;

// @public
export type Condition<TRule> = TRule extends PermissionRule<
  any,
  any,
  infer TResourceType,
  infer TParams
>
  ? undefined extends TParams
    ? () => PermissionCondition<TResourceType, TParams>
    : (params: TParams) => PermissionCondition<TResourceType, TParams>
  : never;

// @public
export type Conditions<
  TRules extends Record<string, PermissionRule<any, any, any>>,
> = {
  [Name in keyof TRules]: Condition<TRules[Name]>;
};

// @public
export type ConditionTransformer<TQuery> = (
  conditions: PermissionCriteria<PermissionCondition>,
) => PermissionCriteria<TQuery>;

// @public
export const createConditionAuthorizer: <TResource, TQuery>(
  rules: PermissionRule<TResource, TQuery, string, PermissionRuleParams>[],
) => (decision: PolicyDecision, resource: TResource | undefined) => boolean;

// @public
export const createConditionExports: <
  TResourceType extends string,
  TResource,
  TRules extends Record<
    string,
    PermissionRule<TResource, any, TResourceType, PermissionRuleParams>
  >,
>(options: {
  pluginId: string;
  resourceType: TResourceType;
  rules: TRules;
}) => {
  conditions: Conditions<TRules>;
  createConditionalDecision: (
    permission: ResourcePermission<TResourceType>,
    conditions: PermissionCriteria<
      PermissionCondition<TResourceType, PermissionRuleParams>
    >,
  ) => ConditionalPolicyDecision;
};

// @public
export const createConditionFactory: <
  TResourceType extends string,
  TParams extends PermissionRuleParams = PermissionRuleParams,
>(
  rule: PermissionRule<unknown, unknown, TResourceType, TParams>,
) => (params: TParams) => PermissionCondition<TResourceType, TParams>;

// @public
export const createConditionTransformer: <
  TQuery,
  TRules extends PermissionRule<any, TQuery, string, PermissionRuleParams>[],
>(
  permissionRules: [...TRules],
) => ConditionTransformer<TQuery>;

// @public
export function createPermissionIntegrationRouter<
  TResourceType1 extends string,
  TResource1,
  TResourceType2 extends string,
  TResource2,
  TResourceType3 extends string,
  TResource3,
>(
  options:
    | {
        permissions: Array<Permission>;
      }
    | CreatePermissionIntegrationRouterResourceOptions<
        TResourceType1,
        TResource1
      >
    | PermissionIntegrationRouterOptions<
        TResourceType1,
        TResource1,
        TResourceType2,
        TResource2,
        TResourceType3,
        TResource3
      >,
): express.Router;

// @public
export type CreatePermissionIntegrationRouterResourceOptions<
  TResourceType extends string,
  TResource,
> = {
  resourceType: TResourceType;
  permissions?: Array<Permission>;
  rules: PermissionRule<TResource, any, NoInfer<TResourceType>>[];
  getResources?: (
    resourceRefs: string[],
  ) => Promise<Array<TResource | undefined>>;
};

// @public
export const createPermissionRule: <
  TResource,
  TQuery,
  TResourceType extends string,
  TParams extends PermissionRuleParams = undefined,
>(
  rule: PermissionRule<TResource, TQuery, TResourceType, TParams>,
) => PermissionRule<TResource, TQuery, TResourceType, TParams>;

// @public
export const isAndCriteria: <T>(
  criteria: PermissionCriteria<T>,
) => criteria is AllOfCriteria<T>;

// @public
export const isNotCriteria: <T>(
  criteria: PermissionCriteria<T>,
) => criteria is NotCriteria<T>;

// @public
export const isOrCriteria: <T>(
  criteria: PermissionCriteria<T>,
) => criteria is AnyOfCriteria<T>;

// @public
export const makeCreatePermissionRule: <
  TResource,
  TQuery,
  TResourceType extends string,
>() => <TParams extends PermissionRuleParams = undefined>(
  rule: PermissionRule<TResource, TQuery, TResourceType, TParams>,
) => PermissionRule<TResource, TQuery, TResourceType, TParams>;

// @public
export type MetadataResponse = {
  permissions?: Permission[];
  rules: MetadataResponseSerializedRule[];
};

// @public
export type MetadataResponseSerializedRule = {
  name: string;
  description: string;
  resourceType: string;
  paramsSchema?: ReturnType<typeof zodToJsonSchema>;
};

// @public
export type PermissionIntegrationRouterOptions<
  TResourceType1 extends string = string,
  TResource1 = any,
  TResourceType2 extends string = string,
  TResource2 = any,
  TResourceType3 extends string = string,
  TResource3 = any,
> = {
  resources: Readonly<
    | [
        CreatePermissionIntegrationRouterResourceOptions<
          TResourceType1,
          TResource1
        >,
      ]
    | [
        CreatePermissionIntegrationRouterResourceOptions<
          TResourceType1,
          TResource1
        >,
        CreatePermissionIntegrationRouterResourceOptions<
          TResourceType2,
          TResource2
        >,
      ]
    | [
        CreatePermissionIntegrationRouterResourceOptions<
          TResourceType1,
          TResource1
        >,
        CreatePermissionIntegrationRouterResourceOptions<
          TResourceType2,
          TResource2
        >,
        CreatePermissionIntegrationRouterResourceOptions<
          TResourceType3,
          TResource3
        >,
      ]
  >;
};

// @public
export interface PermissionPolicy {
  // (undocumented)
  handle(
    request: PolicyQuery,
    user?: BackstageIdentityResponse,
  ): Promise<PolicyDecision>;
}

// @public
export type PermissionRule<
  TResource,
  TQuery,
  TResourceType extends string,
  TParams extends PermissionRuleParams = PermissionRuleParams,
> = {
  name: string;
  description: string;
  resourceType: TResourceType;
  paramsSchema?: z.ZodSchema<TParams>;
  apply(resource: TResource, params: NoInfer<TParams>): boolean;
  toQuery(params: NoInfer<TParams>): PermissionCriteria<TQuery>;
};

// @public
export type PolicyQuery = {
  permission: Permission;
};

// @public
export class ServerPermissionClient implements PermissionEvaluator {
  // (undocumented)
  authorize(
    requests: AuthorizePermissionRequest[],
    options?: EvaluatorRequestOptions,
  ): Promise<AuthorizePermissionResponse[]>;
  // (undocumented)
  authorizeConditional(
    queries: QueryPermissionRequest[],
    options?: EvaluatorRequestOptions,
  ): Promise<PolicyDecision[]>;
  // (undocumented)
  static fromConfig(
    config: Config,
    options: {
      discovery: PluginEndpointDiscovery;
      tokenManager: TokenManager;
    },
  ): ServerPermissionClient;
}
```