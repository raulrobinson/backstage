## API Report File for "@backstage/plugin-azure-devops"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
/// <reference types="react" />

import { ApiRef } from '@backstage/core-plugin-api';
import { BackstagePlugin } from '@backstage/core-plugin-api';
import { BuildRun } from '@backstage/plugin-azure-devops-common';
import { BuildRunOptions } from '@backstage/plugin-azure-devops-common';
import { DashboardPullRequest } from '@backstage/plugin-azure-devops-common';
import { DiscoveryApi } from '@backstage/core-plugin-api';
import { Entity } from '@backstage/catalog-model';
import { GitTag } from '@backstage/plugin-azure-devops-common';
import { IdentityApi } from '@backstage/core-plugin-api';
import { PullRequest } from '@backstage/plugin-azure-devops-common';
import { PullRequestOptions } from '@backstage/plugin-azure-devops-common';
import { Readme } from '@backstage/plugin-azure-devops-common';
import { ReadmeConfig } from '@backstage/plugin-azure-devops-common';
import { RepoBuild } from '@backstage/plugin-azure-devops-common';
import { RepoBuildOptions } from '@backstage/plugin-azure-devops-common';
import { SvgIconProps } from '@material-ui/core';
import { Team } from '@backstage/plugin-azure-devops-common';

// @public (undocumented)
export type AllFilter = BaseFilter & {
  type: FilterType.All;
};

// @public (undocumented)
export type AssignedToTeamFilter = BaseFilter & {
  type: FilterType.AssignedToTeam;
  teamId: string;
};

// @public (undocumented)
export type AssignedToTeamsFilter = BaseFilter &
  (
    | {
        type: FilterType.AssignedToTeams;
        teamIds: string[];
      }
    | {
        type: FilterType.AssignedToCurrentUsersTeams;
        teamIds?: string[];
      }
  );

// @public (undocumented)
export type AssignedToUserFilter = BaseFilter &
  (
    | {
        type: FilterType.AssignedToUser;
        email: string;
      }
    | {
        type: FilterType.AssignedToCurrentUser;
        email?: string;
      }
  );

// @public (undocumented)
export interface AzureDevOpsApi {
  // (undocumented)
  getAllTeams(): Promise<Team[]>;
  // (undocumented)
  getBuildRuns(
    projectName: string,
    repoName?: string,
    definitionName?: string,
    options?: BuildRunOptions,
  ): Promise<{
    items: BuildRun[];
  }>;
  // (undocumented)
  getDashboardPullRequests(
    projectName: string,
  ): Promise<DashboardPullRequest[]>;
  // (undocumented)
  getGitTags(
    projectName: string,
    repoName: string,
  ): Promise<{
    items: GitTag[];
  }>;
  // (undocumented)
  getPullRequests(
    projectName: string,
    repoName: string,
    options?: PullRequestOptions,
  ): Promise<{
    items: PullRequest[];
  }>;
  // (undocumented)
  getReadme(opts: ReadmeConfig): Promise<Readme>;
  // (undocumented)
  getRepoBuilds(
    projectName: string,
    repoName: string,
    options?: RepoBuildOptions,
  ): Promise<{
    items: RepoBuild[];
  }>;
  // (undocumented)
  getUserTeamIds(userId: string): Promise<string[]>;
}

// @public (undocumented)
export const azureDevOpsApiRef: ApiRef<AzureDevOpsApi>;

// @public (undocumented)
export class AzureDevOpsClient implements AzureDevOpsApi {
  constructor(options: {
    discoveryApi: DiscoveryApi;
    identityApi: IdentityApi;
  });
  // (undocumented)
  getAllTeams(): Promise<Team[]>;
  // (undocumented)
  getBuildRuns(
    projectName: string,
    repoName?: string,
    definitionName?: string,
    options?: BuildRunOptions,
  ): Promise<{
    items: BuildRun[];
  }>;
  // (undocumented)
  getDashboardPullRequests(
    projectName: string,
  ): Promise<DashboardPullRequest[]>;
  // (undocumented)
  getGitTags(
    projectName: string,
    repoName: string,
  ): Promise<{
    items: GitTag[];
  }>;
  // (undocumented)
  getPullRequests(
    projectName: string,
    repoName: string,
    options?: PullRequestOptions,
  ): Promise<{
    items: PullRequest[];
  }>;
  // (undocumented)
  getReadme(opts: ReadmeConfig): Promise<Readme>;
  // (undocumented)
  getRepoBuilds(
    projectName: string,
    repoName: string,
    options?: RepoBuildOptions,
  ): Promise<{
    items: RepoBuild[];
  }>;
  // (undocumented)
  getUserTeamIds(userId: string): Promise<string[]>;
}

// @public (undocumented)
export const azureDevOpsPlugin: BackstagePlugin<{}, {}, {}>;

// @public (undocumented)
export const AzurePullRequestsIcon: (props: SvgIconProps) => JSX.Element;

// @public (undocumented)
export const AzurePullRequestsPage: (props: {
  projectName?: string | undefined;
  pollingInterval?: number | undefined;
  defaultColumnConfigs?: PullRequestColumnConfig[] | undefined;
}) => JSX.Element;

// @public (undocumented)
export type BaseFilter = {
  type: FilterType;
};

// @public (undocumented)
export type CreatedByTeamFilter = BaseFilter &
  ({
    type: FilterType.CreatedByTeam;
  } & (
    | {
        teamId: string;
      }
    | {
        teamName: string;
      }
  ));

// @public (undocumented)
export type CreatedByTeamsFilter = BaseFilter &
  (
    | ({
        type: FilterType.CreatedByTeams;
      } & (
        | {
            teamIds: string[];
          }
        | {
            teamNames: string[];
          }
      ))
    | {
        type: FilterType.CreatedByCurrentUsersTeams;
        teamIds?: string[];
      }
  );

// @public (undocumented)
export type CreatedByUserFilter = BaseFilter &
  (
    | {
        type: FilterType.CreatedByUser;
        email: string;
      }
    | {
        type: FilterType.CreatedByCurrentUser;
        email?: string;
      }
  );

// @public (undocumented)
export const EntityAzureGitTagsContent: () => JSX.Element;

// @public (undocumented)
export const EntityAzurePipelinesContent: (props: {
  defaultLimit?: number | undefined;
}) => JSX.Element;

// @public (undocumented)
export const EntityAzurePullRequestsContent: (props: {
  defaultLimit?: number | undefined;
}) => JSX.Element;

// @public (undocumented)
export const EntityAzureReadmeCard: (props: {
  maxHeight?: number | undefined;
}) => JSX.Element;

// @public (undocumented)
export type Filter =
  | AssignedToUserFilter
  | CreatedByUserFilter
  | AssignedToTeamFilter
  | CreatedByTeamFilter
  | AssignedToTeamsFilter
  | CreatedByTeamsFilter
  | AllFilter;

// @public (undocumented)
export enum FilterType {
  // (undocumented)
  All = 'All',
  // (undocumented)
  AssignedToCurrentUser = 'AssignedToCurrentUser',
  // (undocumented)
  AssignedToCurrentUsersTeams = 'AssignedToCurrentUsersTeams',
  // (undocumented)
  AssignedToTeam = 'AssignedToTeam',
  // (undocumented)
  AssignedToTeams = 'AssignedToTeams',
  // (undocumented)
  AssignedToUser = 'AssignedToUser',
  // (undocumented)
  CreatedByCurrentUser = 'CreatedByCurrentUser',
  // (undocumented)
  CreatedByCurrentUsersTeams = 'CreatedByCurrentUsersTeams',
  // (undocumented)
  CreatedByTeam = 'CreatedByTeam',
  // (undocumented)
  CreatedByTeams = 'CreatedByTeams',
  // (undocumented)
  CreatedByUser = 'CreatedByUser',
}

// @public (undocumented)
export const isAzureDevOpsAvailable: (entity: Entity) => boolean;

// @public (undocumented)
export const isAzurePipelinesAvailable: (entity: Entity) => boolean;

// @public (undocumented)
export interface PullRequestColumnConfig {
  // (undocumented)
  filters: Filter[];
  // (undocumented)
  simplified?: boolean;
  // (undocumented)
  title: string;
}

// @public (undocumented)
export type PullRequestFilter = (pullRequest: DashboardPullRequest) => boolean;

// (No @packageDocumentation comment for this package)
```