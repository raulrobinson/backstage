## API Report File for "@backstage/plugin-github-actions"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
/// <reference types="react" />

import { ApiRef } from '@backstage/core-plugin-api';
import { BackstagePlugin } from '@backstage/core-plugin-api';
import { ConfigApi } from '@backstage/core-plugin-api';
import { Entity } from '@backstage/catalog-model';
import { InfoCardVariants } from '@backstage/core-components';
import { RestEndpointMethodTypes } from '@octokit/rest';
import { RouteRef } from '@backstage/core-plugin-api';
import { ScmAuthApi } from '@backstage/integration-react';

// @public (undocumented)
export enum BuildStatus {
  // (undocumented)
  'failure' = 1,
  // (undocumented)
  'pending' = 2,
  // (undocumented)
  'running' = 3,
  // (undocumented)
  'success' = 0,
}

// @public (undocumented)
export const EntityGithubActionsContent: () => JSX.Element;

// @public (undocumented)
export const EntityLatestGithubActionRunCard: (props: {
  branch: string;
  variant?: InfoCardVariants | undefined;
}) => JSX.Element;

// @public (undocumented)
export const EntityLatestGithubActionsForBranchCard: (props: {
  branch: string;
  variant?: InfoCardVariants | undefined;
}) => JSX.Element;

// @public (undocumented)
export const EntityRecentGithubActionsRunsCard: (props: {
  branch?: string | undefined;
  dense?: boolean | undefined;
  limit?: number | undefined;
  variant?: InfoCardVariants | undefined;
}) => JSX.Element;

// @public (undocumented)
export const GITHUB_ACTIONS_ANNOTATION = 'github.com/project-slug';

// @public
export type GithubActionsApi = {
  listWorkflowRuns: (options: {
    hostname?: string;
    owner: string;
    repo: string;
    pageSize?: number;
    page?: number;
    branch?: string;
  }) => Promise<
    RestEndpointMethodTypes['actions']['listWorkflowRuns']['response']['data']
  >;
  getWorkflow: (options: {
    hostname?: string;
    owner: string;
    repo: string;
    id: number;
  }) => Promise<
    RestEndpointMethodTypes['actions']['getWorkflow']['response']['data']
  >;
  getWorkflowRun: (options: {
    hostname?: string;
    owner: string;
    repo: string;
    id: number;
  }) => Promise<
    RestEndpointMethodTypes['actions']['getWorkflowRun']['response']['data']
  >;
  reRunWorkflow: (options: {
    hostname?: string;
    owner: string;
    repo: string;
    runId: number;
  }) => Promise<any>;
  listJobsForWorkflowRun: (options: {
    hostname?: string;
    owner: string;
    repo: string;
    id: number;
    pageSize?: number;
    page?: number;
  }) => Promise<
    RestEndpointMethodTypes['actions']['listJobsForWorkflowRun']['response']['data']
  >;
  downloadJobLogsForWorkflowRun: (options: {
    hostname?: string;
    owner: string;
    repo: string;
    runId: number;
  }) => Promise<
    RestEndpointMethodTypes['actions']['downloadJobLogsForWorkflowRun']['response']['data']
  >;
};

// @public (undocumented)
export const githubActionsApiRef: ApiRef<GithubActionsApi>;

// @public
export class GithubActionsClient implements GithubActionsApi {
  constructor(options: { configApi: ConfigApi; scmAuthApi: ScmAuthApi });
  // (undocumented)
  downloadJobLogsForWorkflowRun(options: {
    hostname?: string;
    owner: string;
    repo: string;
    runId: number;
  }): Promise<
    RestEndpointMethodTypes['actions']['downloadJobLogsForWorkflowRun']['response']['data']
  >;
  // (undocumented)
  getWorkflow(options: {
    hostname?: string;
    owner: string;
    repo: string;
    id: number;
  }): Promise<
    RestEndpointMethodTypes['actions']['getWorkflow']['response']['data']
  >;
  // (undocumented)
  getWorkflowRun(options: {
    hostname?: string;
    owner: string;
    repo: string;
    id: number;
  }): Promise<
    RestEndpointMethodTypes['actions']['getWorkflowRun']['response']['data']
  >;
  // (undocumented)
  listJobsForWorkflowRun(options: {
    hostname?: string;
    owner: string;
    repo: string;
    id: number;
    pageSize?: number;
    page?: number;
  }): Promise<
    RestEndpointMethodTypes['actions']['listJobsForWorkflowRun']['response']['data']
  >;
  // (undocumented)
  listWorkflowRuns(options: {
    hostname?: string;
    owner: string;
    repo: string;
    pageSize?: number;
    page?: number;
    branch?: string;
  }): Promise<
    RestEndpointMethodTypes['actions']['listWorkflowRuns']['response']['data']
  >;
  // (undocumented)
  reRunWorkflow(options: {
    hostname?: string;
    owner: string;
    repo: string;
    runId: number;
  }): Promise<any>;
}

// @public (undocumented)
const githubActionsPlugin: BackstagePlugin<
  {
    entityContent: RouteRef<undefined>;
  },
  {},
  {}
>;
export { githubActionsPlugin };
export { githubActionsPlugin as plugin };

// @public (undocumented)
const isGithubActionsAvailable: (entity: Entity) => boolean;
export { isGithubActionsAvailable };
export { isGithubActionsAvailable as isPluginApplicableToEntity };

// @public (undocumented)
export type Job = {
  html_url?: string;
  status: string;
  conclusion?: string;
  started_at: string;
  completed_at?: string;
  id: number;
  name: string;
  steps?: Step[];
};

// @public (undocumented)
export type Jobs = {
  total_count: number;
  jobs: Job[];
};

// @public (undocumented)
export const LatestWorkflowRunCard: (props: {
  branch: string;
  variant?: InfoCardVariants;
}) => JSX.Element;

// @public (undocumented)
export const LatestWorkflowsForBranchCard: (props: {
  branch: string;
  variant?: InfoCardVariants;
}) => JSX.Element;

// @public (undocumented)
export const RecentWorkflowRunsCard: (props: {
  branch?: string;
  dense?: boolean;
  limit?: number;
  variant?: InfoCardVariants;
}) => JSX.Element;

// @public (undocumented)
export const Router: () => JSX.Element;

// @public (undocumented)
export type Step = {
  name: string;
  status: string;
  conclusion?: string;
  number: number;
  started_at?: string;
  completed_at?: string;
};
```