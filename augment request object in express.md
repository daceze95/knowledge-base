# How to Augment Request Object in Express

Folder structure
----
src/

  types/
  
    express/
    
      index.d.ts
        ```js
          declare global {
            namespace Express {
              interface Request {
                user?: {
                  email: string;
                  fullName: string;
                };
              }
            }
          }
          
          export {};
        ```
    global-types.ts
      ```js
        /// <reference types="../types/express" />
      ```
  app.ts
  
    ```js
       import "./types/global-types"
    ```
  
  tsconfig.json
  
    ```js
      "typeRoots": ["./node_modules/@types", "./src/types"]
    ```
