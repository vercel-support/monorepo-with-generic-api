## Monorepo Structure:

3 projects deployed and 1 common framework

* `packages/docs`: `Next.js` project standalone
* `packages/front`: `Next.js` project that includes the helper function outside it's root folder in `packages/framework` - Look at developer console in the deployed root of the site
* `packages/py-api`: Python API - load `yourdeploylink/api/date.py`

## Setting this up with Vercel CLI

After you have cloned the repository locally, from the root folder, run `vercel link` 3 times.

#### Link the `docs` project

* Run `vercel link` and then choose the name of your project such as `monorepo-docs`
* choose all the default values except for root folder, use `./packages/docs`
* Make sure the framework for the project in the project settings in the Vercel dashboard is set to  `Next.js`
* Run `vercel --prod` to deploy this project

#### Link the `front` project

* Run `vercel link` and then choose the name of your project such as `monorepo-front`
* choose all the default values except for root folder, use `./packages/front`
* Make sure the framework for the project in the project settings in the Vercel dashboard is set to  `Next.js`
* Run `vercel --prod` to deploy this project
* To check if the including of the helper framework in `./packages/framework` is working, go to the deploy http link for this project and open the developer console.

#### Link the `api` project

* Run `vercel link` and then choose the name of your project such as `monorepo-api`
* choose all the default values except for root folder, use `./packages/py-api`
* Run `vercel --prod` to deploy this project
* Go to `project-deploy-link/api/date.py` to see the current returned date
