# nc-typescript-project
Create typescript project with vscode


package.json
```
  "scripts": {
    "test": "jest",
    "test:watch": "jest --watch",
    "start": "ts-node --inspect=9229 src/index.ts",
    "dev": "nodemon"
  },
  "jest": {
    "transform": {
      ".(ts|tsx)": "<rootDir>/node_modules/ts-jest/preprocessor.js"
    },
    "testRegex": "(/__tests__/.*|\\.(test|spec))\\.(ts|tsx|js)$",
    "moduleFileExtensions": [
      "ts",
      "tsx",
      "js",
      "json"
    ]
  },
  
  "devDependencies": {
    "@types/jest": "^22.1.3",
    "@types/node": "^9.4.6",
    "jest": "^22.4.2",
    "nodemon": "^1.17.1",
    "ts-jest": "^22.4.0",
    "ts-node": "^5.0.0",
    "typescript": "^2.7.2"
  }
```

Create src/index.test.ts
```
import "jest"

describe("Jest Tests", () => {
    test("Verify Tests Work", () => {
        expect(true).toBeTruthy()
    })
})
```

Create src/index.ts
```
console.log(‘hello’)
```

Create tsconfig.json
```
{
  "compilerOptions": {
    "module": "commonjs",
    "target": "es5",
    "noImplicitAny": false,
    "sourceMap": true,
    "outDir": "./",
    "esModuleInterop": true,
    "strict": true,
    "typeRoots": [
      "./node_modules/@types"
    ],
    "types": [
      "node"
    ]
  },
  "exclude": [
    "node_modules",
    "**/*.spec.ts",
    "**/*.test.ts"
  ],
  "include": [
    "src/**/*.ts"
  ]
}
```

Create nodemon.json
```
{
  "ignore": ["**/*.test.ts", "**/*.spec.ts", ".git", "node_modules"],
  "watch": ["src"],
  "exec": "npm start",
  "ext": "ts"
}
```

Create .vscode/settings.json
```
{
  "files.exclude": {
    "**/*.js": {
      "when": "$(basename).ts"
    },
    "**/**.js": {
      "when": "$(basename).tsx"
    }
  },
  "typescript.tsdk": "./node_modules/typescript/lib",
  "typescript.referencesCodeLens.enabled": true,
  "typescript.implementationsCodeLens.enabled": true
}
```

Create .vscode/launch.json
```
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "attach",
            "name": "Attach by Process ID",
            "processId": "${command:PickProcess}",
            "restart": true,
            "protocol": "inspector",
            "trace": "verbose"
        },
    ]
}
```

Create .editorconfig
```
# EditorConfig is awesome: http://EditorConfig.org

# top-most EditorConfig file
root = true

# Unix-style newlines with a newline ending every file
[*]
end_of_line = lf
insert_final_newline = true
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true


[*.gradle]
indent_size = 4
```

Create .gitignore
```
node_modules
.idea
```


## Run
> For dev: `npm run dev`
>
> For pro: `npm start`
>
> Test: `npm test`


