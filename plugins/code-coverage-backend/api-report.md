## API Report File for "@backstage/plugin-code-coverage-backend"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
import { CatalogApi } from '@backstage/catalog-client';
import { Config } from '@backstage/config';
import express from 'express';
import { Logger } from 'winston';
import { PluginDatabaseManager } from '@backstage/backend-common';
import { PluginEndpointDiscovery } from '@backstage/backend-common';
import { UrlReader } from '@backstage/backend-common';

// @public
export function createRouter(options: RouterOptions): Promise<express.Router>;

// @public
export interface RouterOptions {
  // (undocumented)
  catalogApi?: CatalogApi;
  // (undocumented)
  config: Config;
  // (undocumented)
  database: PluginDatabaseManager;
  // (undocumented)
  discovery: PluginEndpointDiscovery;
  // (undocumented)
  logger: Logger;
  // (undocumented)
  urlReader: UrlReader;
}
```