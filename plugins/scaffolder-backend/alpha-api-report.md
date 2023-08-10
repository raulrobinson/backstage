## API Report File for "@backstage/plugin-scaffolder-backend"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
import { BackendFeature } from '@backstage/backend-plugin-api';
import { ConditionalPolicyDecision } from '@backstage/plugin-permission-common';
import { Conditions } from '@backstage/plugin-permission-node';
import { JsonObject } from '@backstage/types';
import { PermissionCondition } from '@backstage/plugin-permission-common';
import { PermissionCriteria } from '@backstage/plugin-permission-common';
import { PermissionRule } from '@backstage/plugin-permission-node';
import { PermissionRuleParams } from '@backstage/plugin-permission-common';
import { ResourcePermission } from '@backstage/plugin-permission-common';
import { TaskBroker } from '@backstage/plugin-scaffolder-backend';
import { TemplateAction } from '@backstage/plugin-scaffolder-node';
import { TemplateEntityStepV1beta3 } from '@backstage/plugin-scaffolder-common';
import { TemplateFilter } from '@backstage/plugin-scaffolder-backend';
import { TemplateGlobal } from '@backstage/plugin-scaffolder-backend';
import { TemplateParametersV1beta3 } from '@backstage/plugin-scaffolder-common';

// @alpha
export const catalogModuleTemplateKind: () => BackendFeature;

// @alpha (undocumented)
export const createScaffolderActionConditionalDecision: (
  permission: ResourcePermission<'scaffolder-action'>,
  conditions: PermissionCriteria<
    PermissionCondition<'scaffolder-action', PermissionRuleParams>
  >,
) => ConditionalPolicyDecision;

// @alpha
export const createScaffolderTemplateConditionalDecision: (
  permission: ResourcePermission<'scaffolder-template'>,
  conditions: PermissionCriteria<
    PermissionCondition<'scaffolder-template', PermissionRuleParams>
  >,
) => ConditionalPolicyDecision;

// @alpha
export const scaffolderActionConditions: Conditions<{
  hasActionId: PermissionRule<
    {
      action: string;
      input: JsonObject | undefined;
    },
    {},
    'scaffolder-action',
    {
      actionId: string;
    }
  >;
  hasBooleanProperty: PermissionRule<
    {
      action: string;
      input: JsonObject | undefined;
    },
    {},
    'scaffolder-action',
    {
      key: string;
      value?: boolean | undefined;
    }
  >;
  hasNumberProperty: PermissionRule<
    {
      action: string;
      input: JsonObject | undefined;
    },
    {},
    'scaffolder-action',
    {
      key: string;
      value?: number | undefined;
    }
  >;
  hasStringProperty: PermissionRule<
    {
      action: string;
      input: JsonObject | undefined;
    },
    {},
    'scaffolder-action',
    {
      key: string;
      value?: string | undefined;
    }
  >;
}>;

// @alpha
export const scaffolderPlugin: (
  options?: ScaffolderPluginOptions | undefined,
) => BackendFeature;

// @alpha
export type ScaffolderPluginOptions = {
  actions?: TemplateAction<any, any>[];
  taskWorkers?: number;
  taskBroker?: TaskBroker;
  additionalTemplateFilters?: Record<string, TemplateFilter>;
  additionalTemplateGlobals?: Record<string, TemplateGlobal>;
};

// @alpha
export const scaffolderTemplateConditions: Conditions<{
  hasTag: PermissionRule<
    TemplateParametersV1beta3 | TemplateEntityStepV1beta3,
    {},
    'scaffolder-template',
    {
      tag: string;
    }
  >;
}>;

// (No @packageDocumentation comment for this package)
```