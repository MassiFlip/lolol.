---
subtitle: "[]{#_1s1wrqzx3ke .anchor}Table of Contents"
---

[**Creating an Angular Project from WebStorm
3**](#creating-an-angular-project-from-webstorm)

[**Creating an Angular Project from Terminal
3**](#creating-an-angular-project-from-terminal)

[**Mac - Admin Password 3**](#mac---admin-password)

[**Mac - Updating File Ownership and Permissions
4**](#mac---updating-file-ownership-and-permissions)

[**Update package.json 4**](#update-package.json)

[**Install Angular Material 5**](#install-angular-material)

[**Configure i18n 7**](#configure-i18n)

[**Create LanguageSwitcher Component
10**](#create-languageswitcher-component)

[**Create Home Component 12**](#create-home-component)

[**Create About Component 12**](#create-about-component)

[**Create PageNotFound Component 13**](#create-pagenotfound-component)

[**Create FooterContent Component 15**](#create-footercontent-component)

[**Create Layout Component 16**](#create-layout-component)

[**Update app.routes.ts 17**](#update-app.routes.ts)

[**Update App Component 18**](#update-app-component)

[**Configure Fake API with json-server
18**](#configure-fake-api-with-json-server)

[**Add Environments Variables 22**](#add-environments-variables)

[**Create Base Entity Interface 22**](#create-base-entity-interface)

[**Create Category Entity 23**](#create-category-entity)

[**Create Course Entity 24**](#create-course-entity)

[**Create Base Response 28**](#create-base-response)

[**Create Base Assembler 29**](#create-base-assembler)

[**Create BaseApi Endpoint 30**](#create-baseapi-endpoint)

[**Create BaseApi 33**](#create-baseapi)

[**Create Categories Response 34**](#create-categories-response)

[**Create Courses Response 35**](#create-courses-response)

[**Create Category Assembler 36**](#create-category-assembler)

[**Create Course Assembler 38**](#create-course-assembler)

[**Create CategoriesApi Endpoint 39**](#create-categoriesapi-endpoint)

[**Create CoursesApi Endpoint 40**](#create-coursesapi-endpoint)

[**Create LearningApi 41**](#create-learningapi)

[**Create LearningStore 44**](#create-learningstore)

[**Create CategoryForm Component 49**](#create-categoryform-component)

[**Create CategoryList Component 52**](#create-categorylist-component)

[**Create CourseForm Component 54**](#create-courseform-component)

[**Create CourseList Component 57**](#create-courselist-component)

[**Create learning.routes.ts‎ 60**](#create-learning.routes.ts)

[**Update i18n files & Add categories and courses to layout options.
61**](#update-i18n-files-add-categories-and-courses-to-layout-options.)

[**Update LearningStore 64**](#update-learningstore)

[**Update i18n files 69**](#update-i18n-files)

[**Update learning.routes.ts‎ 73**](#update-learning.routes.ts)

[**Update CategoryForm 74**](#update-categoryform)

[**Update CategoryList 76**](#update-categorylist)

[**Update CourseAssembler 79**](#update-courseassembler)

[**Update CourseForm 80**](#update-courseform)

[**Update CourseList 84**](#update-courselist)

[**MockAPI 88**](#mockapi)

#  

# Creating an Angular Project from WebStorm

-   Click File → New → Project\...

```{=html}
<!-- -->
```
-   In the New Project window, select Angular CLI from the left panel.

-   Configure the project as shown below, then click Create.

# ![](media/image6.png){width="6.267716535433071in" height="5.097222222222222in"}

# Creating an Angular Project from Terminal

+-----------------------------------------------------------------------+
| cd Documents                                                          |
|                                                                       |
| sudo ng new learning-center \--defaults \--standalone                 |
|                                                                       |
| cd learning-center                                                    |
|                                                                       |
| webstorm .                                                            |
+=======================================================================+
+-----------------------------------------------------------------------+

# Mac - Admin Password

UPC0000

# Mac - Updating File Ownership and Permissions

+-----------------------------------------------------------------------+
| sudo chown -R alumnos:staff \~/Documents                              |
|                                                                       |
| sudo chown -R alumnos:staff \~/Documents/learning-center\             |
| sudo chown alumnos \~/.zshrc                                          |
|                                                                       |
| chmod u+rw \~/.zshrc\                                                 |
| sudo chown alumnos \~/.angular-config.json                            |
+=======================================================================+
+-----------------------------------------------------------------------+

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"chore: initial commit.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update package.json

-   Replace package.json with the following code:

  -----------------------------------------------------------------------
  {\
  \"name\": \"learning-center\",\
  \"version\": \"1.0.0\",\
  \"description\": \"ACME Learning Center Application\",\
  \"author\": \"Open-Source Applications Development Team\",\
  \"license\": \"MIT\",\
  \"scripts\": {\
  \"ng\": \"ng\",\
  \"start\": \"ng serve\",\
  \"build\": \"ng build\",\
  \"watch\": \"ng build \--watch \--configuration development\",\
  \"test\": \"ng test\"\
  },\
  \"prettier\": {\
  \"printWidth\": 100,\
  \"singleQuote\": true,\
  \"overrides\": \[\
  {\
  \"files\": \"\*.html\",\
  \"options\": {\
  \"parser\": \"angular\"\
  }\
  }\
  \]\
  },\
  \"private\": true,\
  \"dependencies\": {\
  \"@angular/common\": \"\^20.3.0\",\
  \"@angular/compiler\": \"\^20.3.0\",\
  \"@angular/core\": \"\^20.3.0\",\
  \"@angular/forms\": \"\^20.3.0\",\
  \"@angular/platform-browser\": \"\^20.3.0\",\
  \"@angular/router\": \"\^20.3.0\",\
  \"rxjs\": \"\~7.8.0\",\
  \"tslib\": \"\^2.3.0\",\
  \"zone.js\": \"\~0.15.0\"\
  },\
  \"devDependencies\": {\
  \"@angular/build\": \"\^20.3.2\",\
  \"@angular/cli\": \"\^20.3.2\",\
  \"@angular/compiler-cli\": \"\^20.3.0\",\
  \"@types/jasmine\": \"\~5.1.0\",\
  \"jasmine-core\": \"\~5.9.0\",\
  \"karma\": \"\~6.4.0\",\
  \"karma-chrome-launcher\": \"\~3.2.0\",\
  \"karma-coverage\": \"\~2.2.0\",\
  \"karma-jasmine\": \"\~5.1.0\",\
  \"karma-jasmine-html-reporter\": \"\~2.1.0\",\
  \"typescript\": \"\~5.9.2\"\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"chore: update package.json with version, metadata, and
  license.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Install Angular Material

-   Add Angular Material

  -----------------------------------------------------------------------
  ng add \@angular/material
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace styles.css with the following code:

  -----------------------------------------------------------------------
  \@import \'./custom-theme.scss\'; /\* You can add global styles to this
  file, and also import other style files \*/\
  \
  html, body {\
  height: 100%;\
  }\
  \
  body {\
  margin: 0;\
  font-family: Roboto, \"Helvetica Neue\", sans-serif;\
  }\
  \
  .container-with-spacing {\
  margin: 10px; /\* Applies margin to all sides \*/\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace custom-theme.scss with the following code:

  -----------------------------------------------------------------------
  // Include theming for Angular Material with \`mat.theme()\`.\
  // This Sass mixin will define CSS variables that are used for styling
  Angular Material\
  // components according to the Material 3 design spec.\
  // Learn more about theming and how to use it for your application\'s\
  // custom components at https://material.angular.dev/guide/theming\
  \@use \'@angular/material\' as mat;\
  \@include mat.core();\
  \
  :root {\
  \@include mat.toolbar-overrides((container-background-color: slategray,
  container-text-color: white));\
  }\
  \
  html {\
  \@include mat.theme((\
  color: (\
  primary: mat.\$azure-palette,\
  tertiary: mat.\$blue-palette,\
  ),\
  typography: Roboto,\
  density: 0,\
  ));\
  }\
  \
  body {\
  // Default the application to a light color theme. This can be changed
  to\
  // \`dark\` to enable the dark color theme, or to \`light dark\` to
  defer to the\
  // user\'s system settings.\
  color-scheme: light;\
  \
  // Set a default background, font and text colors for the application
  using\
  // Angular Material\'s system-level CSS variables. Learn more about
  these\
  // variables at https://material.angular.dev/guide/system-variables\
  background-color: var(\--mat-sys-surface);\
  color: var(\--mat-sys-on-surface);\
  font: var(\--mat-sys-body-medium);\
  \
  // Reset the user agent margin.\
  margin: 0;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"chore: integrate angular material and update styles.\"
  -m \"- Add custom theme and Roboto font.\
  - Update dependencies for Angular Material and CDK in package.json.\
  - Disable Angular CLI analytics.\
  - Update version and license in package-lock.json.\
  - Add global styles for consistent appearance.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Configure i18n

  -----------------------------------------------------------------------
  npm i \@ngx-translate/core \@ngx-translate/http-loader
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Right-click on public folder → New → File

-   Enter i18n/en.json and press Enter

-   Add the following code:

  -----------------------------------------------------------------------
  {\
  \"option\": {\
  \"home\": \"Home\",\
  \"about\": \"About Us\"\
  },\
  \"about\": {\
  \"title\": \"About us\",\
  \"content\": \"ACME Learning Center is an Education Platform, part of
  ACME Corporation.\"\
  },\
  \"home\": {\
  \"title\": \"Welcome\",\
  \"content\": \"Welcome to ACME Learning Center.\"\
  },\
  \"page-not-found\": {\
  \"title\": \"Page not found\",\
  \"content\": \"The path \<strong\>{{ invalid_path }}\</strong\> is not
  valid.\",\
  \"go-home\": \"Go Home\"\
  },\
  \"footer\": {\
  \"rights\": \"All rights reserved.\",\
  \"powered-by\": \"Powered by\",\
  \"and\": \"and\"\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Right-click on i18n folder → New → File

-   Enter es.json and press Enter

-   Add the following code:

  -----------------------------------------------------------------------
  {\
  \"option\" : {\
  \"home\": \"Inicio\",\
  \"about\": \"Acerca de\"\
  },\
  \"about\": {\
  \"title\": \"Acerca de nosotros\",\
  \"content\": \"ACME Learning Center es una plataforma educativa, parte
  de ACME Corporation.\"\
  },\
  \"home\": {\
  \"title\": \"Bienvenido\",\
  \"content\": \"Bienvenido a ACME Learning Center.\"\
  },\
  \"page-not-found\": {\
  \"title\": \"Página no encontrada\",\
  \"content\": \"La ruta \<strong\>{{ invalid_path }}\</strong\> es
  inválida.\",\
  \"go-home\": \"Ir a Inicio\"\
  },\
  \"footer\": {\
  \"rights\": \"Todos los derechos reservados.\",\
  \"powered-by\": \"Desarrollado con\",\
  \"and\": \"y\"\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace app.config.ts with the following code:

  -----------------------------------------------------------------------
  import { ApplicationConfig, provideBrowserGlobalErrorListeners,
  provideZoneChangeDetection } from \'@angular/core\';\
  import { provideRouter } from \'@angular/router\';\
  \
  import { routes } from \'./app.routes\';\
  import {provideHttpClient, withFetch} from \'@angular/common/http\';\
  import {provideTranslateService} from \'@ngx-translate/core\';\
  import {provideTranslateHttpLoader} from
  \'@ngx-translate/http-loader\';\
  \
  export const appConfig: ApplicationConfig = {\
  providers: \[\
  provideBrowserGlobalErrorListeners(),\
  provideZoneChangeDetection({ eventCoalescing: true }),\
  provideHttpClient(withFetch()),\
  provideTranslateService({\
  loader: provideTranslateHttpLoader({ prefix: \'./i18n/\', suffix:
  \'.json\' }),\
  fallbackLang: \'en\'\
  }),\
  provideRouter(routes)\
  \]\
  };
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace app.ts with the following code:

  -----------------------------------------------------------------------
  import {Component, inject, signal} from \'@angular/core\';\
  import {TranslateService} from \'@ngx-translate/core\';\
  \
  \@Component({\
  selector: \'app-root\',\
  imports: \[\],\
  templateUrl: \'./app.html\',\
  styleUrl: \'./app.css\'\
  })\
  export class App {\
  protected readonly title = signal(\'learning-center\');\
  private translate: TranslateService;\
  \
  constructor() {\
  this.translate = inject(TranslateService);\
  this.translate.addLangs(\[\'en\', \'es\'\]);\
  this.translate.use(\'en\');\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"chore: add ngx-translate for internationalization
  support.\" -m \"- Integrate \`@ngx-translate/core\` and
  \`@ngx-translate/http-loader\` for i18n.\
  - Configure default and fallback languages in app.config.ts.\
  - Add placeholder translation files for English and Spanish.\
  - Update package.json and package-lock.json with new dependencies.\
  - inject translate service in app component and configure default
  language.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create LanguageSwitcher Component

-   Generate LanguageSwitcher Component

  -----------------------------------------------------------------------
  ng g c shared/presentation/components/LanguageSwitcher \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace language-switcher.ts with the following code:

  -----------------------------------------------------------------------
  import {Component, inject} from \'@angular/core\';\
  import {MatButtonToggle, MatButtonToggleGroup} from
  \'@angular/material/button-toggle\';\
  import {TranslateService} from \'@ngx-translate/core\';\
  \
  \@Component({\
  selector: \'app-language-switcher\',\
  imports: \[\
  MatButtonToggleGroup,\
  MatButtonToggle\
  \],\
  templateUrl: \'./language-switcher.html\',\
  styleUrl: \'./language-switcher.css\'\
  })\
  export class LanguageSwitcher {\
  protected currentLang: string = \'en\';\
  \
  /\*\* List of available language codes \*/\
  protected languages: string\[\] = \[\'en\', \'es\'\];\
  /\*\* Translation service instance \*/\
  private translate: TranslateService;\
  \
  /\*\*\
  \* Creates an instance of LanguageSwitcherComponent.\
  \* Initializes the current language from the translation service.\
  \*/\
  constructor() {\
  this.translate = inject(TranslateService);\
  this.currentLang = this.translate.getCurrentLang();\
  }\
  \
  /\*\*\
  \* Changes the application\'s current language.\
  \* Updates both the translation service and the component\'s local
  state.\
  \*\
  \* \@param language - The language code to switch to (e.g., \'en\',
  \'es\')\
  \*/\
  useLanguage(language: string) {\
  this.translate.use(language);\
  this.currentLang = language;\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace language-switcher.html with the following code:

  -----------------------------------------------------------------------
  \<**mat-button-toggle-group** \[value\]=\"currentLang\"\
  appearance=\"standard\"\
  aria-label=\"Preferred language\"\
  name=\"language\"\>\
  \@for (language of languages; track language) {\
  \<**mat-button-toggle** \[value\]=\"language\"\
  \[aria-label\]=\"language\"\
  (click)=\"useLanguage(language)\"\>\
  {{ language.toUpperCase() }}\
  \</**mat-button-toggle**\>\
  }\
  \</**mat-button-toggle-group**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(shared): add language-switcher component for
  language selection.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Home Component

-   Generate Home Component

  -----------------------------------------------------------------------
  ng g c shared/presentation/views/Home \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace home.ts with the following code:

  -----------------------------------------------------------------------
  import { Component } from \'@angular/core\';\
  import {TranslatePipe} from \'@ngx-translate/core\';\
  \
  \@Component({\
  selector: \'app-home\',\
  imports: \[\
  TranslatePipe\
  \],\
  templateUrl: \'./home.html\',\
  styleUrl: \'./home.css\'\
  })\
  export class Home {\
  \
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace home.html with the following code:

  -----------------------------------------------------------------------
  \<**div** class=\"container-with-spacing\"\>\
  \<**h1**\>{{ \'home.title\' \| translate }}\</**h1**\>\
  \<**p**\>{{ \'home.content\' \| translate }}\</**p**\>\
  \</**div**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(home): add home component with initial structure
  and styles.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create About Component

-   Generate About Component

  -----------------------------------------------------------------------
  ng g c shared/presentation/views/About \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace about.ts with the following code:

  -----------------------------------------------------------------------
  import { Component } from \'@angular/core\';\
  import {TranslatePipe} from \'@ngx-translate/core\';\
  \
  \@Component({\
  selector: \'app-about\',\
  imports: \[\
  TranslatePipe\
  \],\
  templateUrl: \'./about.html\',\
  styleUrl: \'./about.css\'\
  })\
  export class About {\
  \
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace about.html with the following code:

  -----------------------------------------------------------------------
  \<**div** class=\"container-with-spacing\"\>\
  \<**h1**\>{{ \'about.title\' \| translate }}\</**h1**\>\
  \<**img** src=\"/acme-logo.svg\" class=\"logo\"/\>\
  \<**p**\>{{ \'about.content\' \| translate }}\</**p**\>\
  \</**div**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace about.css with the following code:

  -----------------------------------------------------------------------
  .logo {\
  height: 10em;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(about): add about component with initial structure
  and styles.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create PageNotFound Component

-   Generate PageNotFound Component

  -----------------------------------------------------------------------
  ng g c shared/presentation/views/PageNotFound \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace page-not-found.ts with the following code:

  -----------------------------------------------------------------------
  import {Component, inject, OnInit} from \'@angular/core\';\
  import {ActivatedRoute, Router} from \'@angular/router\';\
  import {MatButton} from \'@angular/material/button\';\
  import {TranslatePipe} from \'@ngx-translate/core\';\
  \
  \@Component({\
  selector: \'app-page-not-found\',\
  imports: \[MatButton, TranslatePipe\],\
  templateUrl: \'./page-not-found.html\',\
  styleUrl: \'./page-not-found.css\'\
  })\
  export class PageNotFound implements OnInit {\
  protected invalidPath: string = \'\';\
  private route: ActivatedRoute = inject(ActivatedRoute);\
  private router: Router = inject(Router);\
  \
  ngOnInit() {\
  this.invalidPath = this.route.snapshot.url.map(url =\>
  url.path).join(\'/\');\
  }\
  \
  protected navigateToHome() {\
  this.router.navigate(\[\'home\'\]).then();\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace page-not-found.html with the following code:

  -----------------------------------------------------------------------
  \<**div** class=\"container-with-spacing\"\>\
  \<**h1**\>{{ \'page-not-found.title\' \| translate }}\</**h1**\>\
  \<**div** \[innerHTML\]=\"\'page-not-found.content\' \| translate: {
  invalid_path: invalidPath }\"\>\</**div**\>\
  \</**div**\>\
  \<**button** mat-button (click)=\"navigateToHome()\"\>{{
  \'page-not-found.go-home\' \| translate }}\</**button**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(shared): add page-not-found component with
  structure and navigation.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create FooterContent Component

-   Generate FooterContent Component

  -----------------------------------------------------------------------
  ng g c shared/presentation/components/FooterContent \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace footer-content.ts with the following code:

  -----------------------------------------------------------------------
  import { Component } from \'@angular/core\';\
  import {TranslatePipe} from \'@ngx-translate/core\';\
  \
  \@Component({\
  selector: \'app-footer-content\',\
  imports: \[\
  TranslatePipe\
  \],\
  templateUrl: \'./footer-content.html\',\
  styleUrl: \'./footer-content.css\'\
  })\
  export class FooterContent {\
  \
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace footer-content.html with the following code:

  -----------------------------------------------------------------------
  \<**div** class=\"footer-content\"\>\
  \<**p**\>Copyright &copy; 2025 ACME Studios. {{ \'footer.rights\' \|
  translate}}\</**p**\>\
  \<**p**\>{{ \'footer.powered-by\'\|translate }} \<**a**
  href=\"https://material.angular.dev/\" target=\"\_blank\"\>Angular
  Material\</**a**\> {{\'footer.and\'\|translate}}\
  \<**a** href=\"https://ngx-translate.org/\"
  target=\"\_blank\"\>ngx-translate\</**a**\> \</**p**\>\
  \</**div**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace footer-content.css with the following code:

  -----------------------------------------------------------------------
  .footer-content {\
  position: absolute;\
  bottom: 0;\
  width: 100%;\
  height: 80px;\
  background-color: slategray;\
  color: white;\
  text-align: center;\
  margin: 0;\
  padding: 5px;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(layout): add footer-content component.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Layout Component

-   Generate Layout Component

  -----------------------------------------------------------------------
  ng g c shared/presentation/components/Layout \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace layout.ts with the following code:

  -----------------------------------------------------------------------
  import {Component, inject} from \'@angular/core\';\
  import {RouterLink, RouterLinkActive, RouterOutlet} from
  \'@angular/router\';\
  import {MatToolbar, MatToolbarRow} from \'@angular/material/toolbar\';\
  import {MatButton} from \'@angular/material/button\';\
  import {TranslatePipe} from \'@ngx-translate/core\';\
  import {LanguageSwitcher} from
  \'../language-switcher/language-switcher\';\
  import {FooterContent} from \'../footer-content/footer-content\';\
  \
  \@Component({\
  selector: \'app-layout\',\
  imports: \[\
  RouterOutlet,\
  RouterLink,\
  MatToolbarRow,\
  MatToolbar,\
  MatButton,\
  RouterLinkActive,\
  TranslatePipe,\
  LanguageSwitcher,\
  FooterContent\
  \],\
  templateUrl: \'./layout.html\',\
  styleUrl: \'./layout.css\'\
  })\
  export class Layout {\
  options = \[\
  {link: \'/home\', label: \'option.home\'},\
  {link: \'/about\', label: \'option.about\'}\
  \]\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace layout.html with the following code:

  -----------------------------------------------------------------------
  \<**mat-toolbar**\>\
  \<**mat-toolbar-row**\>\
  \<**h1**\>ACME Learning Center\</**h1**\>\
  \<**div** class=\"mat-spacer\"\>\</**div**\>\
  \@for (option of options; track option.label) {\
  \<**a** mat-button \[routerLink\]=\"option.link\"
  routerLinkActive=\"active\"\>{{ option.label \| translate }}\</**a**\>\
  }\
  \<**app-language-switcher**/\>\
  \</**mat-toolbar-row**\>\
  \</**mat-toolbar**\>\
  \<**router-outlet**/\>\
  \<**app-footer-content**/\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace layout.css with the following code:

  -----------------------------------------------------------------------
  .mat-spacer {\
  flex: 1 1 auto;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(layout): add layout component with structure and
  navigation.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update app.routes.ts

  ------------------------------------------------------------------------------
  import { Routes } from \'@angular/router\';\
  import {Home} from \'./shared/presentation/views/home/home\';\
  \
  const about = () =\>
  import(\'./shared/presentation/views/about/about\').then(m =\> m.About);\
  const pageNotFound = () =\>
  import(\'./shared/presentation/views/page-not-found/page-not-found\').then(m
  =\> m.PageNotFound);\
  const baseTitle = \'ACME Learning Center\';\
  export const routes: Routes = \[\
  { path: \'home\', component: Home, title: \`\${baseTitle} - Home\` },\
  { path: \'about\', loadComponent: about, title: \`\${baseTitle} - About\` },\
  { path: \'\', redirectTo: \'/home\', pathMatch: \'full\' },\
  { path: \'\*\*\', loadComponent: pageNotFound, title: \`\${baseTitle} - Page
  Not Found\` },\
  \];
  ------------------------------------------------------------------------------

  ------------------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"chore: define app routes with lazy loading and page
  titles.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update App Component

-   Replace app.html with the following code:

  -----------------------------------------------------------------------
  \<**app-layout**/\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   npm start

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"\
  chore: clean up app.html by removing template content.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Configure Fake API with json-server

  -----------------------------------------------------------------------
  npm i -g json-server@0.17.4
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Right-click on learning-center project → New → File

-   Enter server/db.json and press Enter

-   Add the following code:

  -----------------------------------------------------------------------
  {\
  \"categories\": \[\
  {\
  \"id\": 1,\
  \"name\": \"Java\"\
  },\
  {\
  \"id\": 2,\
  \"name\": \"Spring Boot\"\
  },\
  {\
  \"id\": 3,\
  \"name\": \"TypeScript\"\
  },\
  {\
  \"id\": 4,\
  \"name\": \"Angular\"\
  },\
  {\
  \"id\": 5,\
  \"name\": \"RESTful\"\
  }\
  \],\
  \"courses\": \[\
  {\
  \"id\": 1,\
  \"title\": \"Java for Beginners\",\
  \"description\": \"An introductory course to Java programming
  language.\"\
  },\
  {\
  \"id\": 2,\
  \"title\": \"Advanced Java Concepts\",\
  \"description\": \"A deep dive into advanced Java programming
  topics.\",\
  \"categoryId\": 1\
  },\
  {\
  \"id\": 3,\
  \"title\": \"Spring Boot Fundamentals\",\
  \"description\": \"Learn the basics of Spring Boot framework.\",\
  \"categoryId\": 2\
  },\
  {\
  \"id\": 4,\
  \"title\": \"Building RESTful APIs with Spring Boot\",\
  \"description\": \"Create robust RESTful APIs using Spring Boot.\",\
  \"categoryId\": 2\
  },\
  {\
  \"id\": 5,\
  \"title\": \"TypeScript Essentials\",\
  \"description\": \"Get started with TypeScript and its features.\",\
  \"categoryId\": 3\
  },\
  {\
  \"id\": 6,\
  \"title\": \"Advanced TypeScript\",\
  \"description\": \"Explore advanced concepts in TypeScript
  programming.\",\
  \"categoryId\": 3\
  },\
  {\
  \"id\": 7,\
  \"title\": \"Angular for Beginners\",\
  \"description\": \"An introductory course to Angular framework.\",\
  \"categoryId\": 4\
  },\
  {\
  \"id\": 8,\
  \"title\": \"Building SPAs with Angular\",\
  \"description\": \"Learn how to build Single Page Applications using
  Angular.\",\
  \"categoryId\": 4\
  },\
  {\
  \"id\": 9,\
  \"title\": \"RESTful Web Services\",\
  \"description\": \"Understand the principles of RESTful web
  services.\",\
  \"categoryId\": 5\
  },\
  {\
  \"id\": 10,\
  \"title\": \"Consuming RESTful APIs\",\
  \"description\": \"Learn how to consume RESTful APIs in your
  applications.\",\
  \"categoryId\": 5\
  },\
  {\
  \"id\": 11,\
  \"title\": \"Full-Stack Development with Java and Angular\",\
  \"description\": \"Combine Java backend with Angular frontend for
  full-stack development.\",\
  \"categoryId\": 1\
  },\
  {\
  \"id\": 12,\
  \"title\": \"Microservices with Spring Boot\",\
  \"description\": \"Build microservices architecture using Spring
  Boot.\",\
  \"categoryId\": 2\
  }\
  \]\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Right-click on server folder → New → File

-   Enter routes.json and press Enter

-   Add the following code:

  -----------------------------------------------------------------------
  {\
  \"/api/v1/\*\": \"/\$1\"\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Right-click on server folder → New → File and enter start.sh and
    > press Enter

-   Add the following code:

  -----------------------------------------------------------------------
  json-server \--watch db.json \--routes routes.json
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Execute start.sh

  -----------------------------------------------------------------------
  cd server\
  sh start.sh
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Right-click on server folder → New → File and enter start.bat and
    > press Enter

-   Add the following code:

  -----------------------------------------------------------------------
  json-server \--watch db.json \--routes routes.json
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Execute start.bat

  -----------------------------------------------------------------------
  cd server\
  ./start.bat
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   [[http://localhost:3000/]{.underline}](http://localhost:3000/)

-   [[http://localhost:3000/api/v1/courses]{.underline}](http://localhost:3000/api/v1/courses)

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(fake-api): add json-server and configure fake
  api.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Add Environments Variables

  -----------------------------------------------------------------------
  ng g environments
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace src/environments/environment.development.ts with the
    > following code:

  -----------------------------------------------------------------------
  export const environment = {\
  production: false,\
  platformProviderApiBaseUrl: \'http://localhost:3000/api/v1\',\
  platformProviderCategoriesEndpointPath: \'/categories\',\
  platformProviderCoursesEndpointPath: \'/courses\',\
  logoProviderApiBaseUrl: \'https://logo.clearbit.com/\'\
  };
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace src/environments/environment.ts with the following code:

  -----------------------------------------------------------------------
  export const environment = {\
  production: true,\
  platformProviderApiBaseUrl: \'http://localhost:3000/api/v1\',\
  platformProviderCategoriesEndpointPath: \'/categories\',\
  platformProviderCoursesEndpointPath: \'/courses\',\
  logoProviderApiBaseUrl: \'https://logo.clearbit.com/\'\
  };
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(env): add environment configuration files for
  production and development.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Base Entity Interface

-   Generate Base Entity Interface

  -----------------------------------------------------------------------
  ng g interface shared/infrastructure/BaseEntity
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace base-entity.ts with the following code:

  -----------------------------------------------------------------------
  /\*\*\
  \* Defines a standard structure for entities with a unique identifier.\
  \*/\
  export interface BaseEntity {\
  /\*\*\
  \* The unique identifier for the entity.\
  \*/\
  id: number;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(shared): add base entity interface for
  standardized entity structure.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Category Entity

-   Generate Category Entity

  -----------------------------------------------------------------------
  ng g class learning/domain/model/Category \--type=entity \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace category.entity.ts with the following code:

  -----------------------------------------------------------------------
  import {BaseEntity} from
  \'../../../shared/infrastructure/base-entity\';\
  \
  /\*\*\
  \* Represents a Category entity in the application.\
  \* \@remarks\
  \* This class is used as a domain model for categories in the learning
  context.\
  \* It implements the BaseEntity interface to ensure consistency across
  entities.\
  \* \@see {@link BaseEntity}\
  \*/\
  export class Category implements BaseEntity {\
  /\*\*\
  \* Creates a new Category instance.\
  \* \@param category - An object containing the id and name of the
  category.\
  \* \@returns A new instance of Category.\
  \*/\
  constructor(category: { id: number; name: string }) {\
  this.\_id = category.id;\
  this.\_name = category.name;\
  }\
  \
  /\*\*\
  \* The unique identifier for the category.\
  \*/\
  private \_id: number;\
  \
  get id(): number {\
  return this.\_id;\
  }\
  \
  set id(value: number) {\
  this.\_id = value;\
  }\
  \
  /\*\*\
  \* The name of the category.\
  \*/\
  private \_name: string;\
  \
  get name(): string {\
  return this.\_name;\
  }\
  \
  set name(value: string) {\
  this.\_name = value;\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add category entity model for learning
  context.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Course Entity

-   Generate Course Entity

  -----------------------------------------------------------------------
  ng g class learning/domain/model/Course \--type=entity \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace course.entity.ts with the following code:

  -----------------------------------------------------------------------
  import {Category} from \'./category.entity\';\
  \
  /\*\*\
  \* Represents a course entity with id, title, description, and
  category.\
  \*\
  \* \@remarks\
  \* This class is used as a domain model for courses in the learning
  context.\
  \* It encapsulates the properties and behaviors associated with a
  course, including its category association.\
  \*\
  \* \@example\
  \* \`\`\`typescript\
  \* const course = new Course({ id: 1, title: \'Introduction to
  TypeScript\', description: \'Learn the basics of TypeScript.\',
  categoryId: 2 });\
  \* console.log(course.id); // Output: 1\
  \* console.log(course.title); // Output: Introduction to TypeScript\
  \* course.categoryId = 3;\
  \* \`\`\`\
  \*/\
  export class Course {\
  /\*\*\
  \* The category associated with the course.\
  \* \@remarks\
  \* This is an object reference to the {@link Category} entity. It may
  be null if not set.\
  \*/\
  get category(): Category \| null {\
  return this.\_category;\
  }\
  \
  /\*\*\
  \* Sets the category associated with the course.\
  \*\
  \* \@param value - The {@link Category} to associate with the course.\
  \*/\
  set category(value: Category \| null) {\
  this.\_category = value;\
  }\
  \
  /\*\*\
  \* Unique identifier for the course.\
  \* \@defaultValue 0\
  \*/\
  private \_id: number;\
  \
  /\*\*\
  \* Title of the course.\
  \* \@defaultValue \'\'\
  \*/\
  private \_title: string;\
  \
  /\*\*\
  \* Description of the course.\
  \* \@defaultValue \'\'\
  \*/\
  private \_description: string;\
  \
  /\*\*\
  \* Identifier of the category associated with the course.\
  \* \@defaultValue 0\
  \*/\
  private \_categoryId: number;\
  \
  /\*\*\
  \* The category object associated with the course, or null if not set.\
  \* \@defaultValue null\
  \*/\
  private \_category: Category \| null;\
  \
  /\*\*\
  \* Creates a new instance of the Course class.\
  \*\
  \* \@param course - An object containing optional properties to
  initialize the course.\
  \* \@param course.id - The unique identifier for the course.\
  \* \@param course.title - The title of the course.\
  \* \@param course.description - The description of the course.\
  \* \@param course.categoryId - The identifier of the category
  associated with the course.\
  \*/\
  constructor(course: { id: number; title: string; description: string;
  categoryId: number; category?: Category \| null }) {\
  this.\_id = course.id;\
  this.\_title = course.title;\
  this.\_description = course.description;\
  this.\_categoryId = course.categoryId;\
  this.\_category = course.category ?? null;\
  }\
  \
  /\*\*\
  \* Gets the course id.\
  \* \@returns The unique identifier for the course.\
  \*/\
  get id(): number {\
  return this.\_id;\
  }\
  \
  /\*\*\
  \* Sets the course id.\
  \* \@param value - The unique identifier to set for the course.\
  \*/\
  set id(value: number) {\
  this.\_id = value;\
  }\
  \
  /\*\*\
  \* Gets the course title.\
  \* \@returns The title of the course.\
  \*/\
  get title(): string {\
  return this.\_title;\
  }\
  \
  /\*\*\
  \* Sets the course title.\
  \* \@param value - The title to set for the course.\
  \*/\
  set title(value: string) {\
  this.\_title = value;\
  }\
  \
  /\*\*\
  \* Gets the course description.\
  \* \@returns The description of the course.\
  \*/\
  get description(): string {\
  return this.\_description;\
  }\
  \
  /\*\*\
  \* Sets the course description.\
  \* \@param value - The description to set for the course.\
  \*/\
  set description(value: string) {\
  this.\_description = value;\
  }\
  \
  /\*\*\
  \* Gets the category id associated with the course.\
  \* \@returns The identifier of the category.\
  \*/\
  get categoryId(): number {\
  return this.\_categoryId;\
  }\
  \
  /\*\*\
  \* Sets the category id associated with the course.\
  \* \@param value - The identifier of the category to associate with the
  course.\
  \*/\
  set categoryId(value: number) {\
  this.\_categoryId = value;\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(courses): add course entity model for learning
  context.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Base Response

-   Generate Base Response Interface

  -----------------------------------------------------------------------
  ng g interface shared/infrastructure/BaseResponse
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace base-response.ts with the following code:

  -----------------------------------------------------------------------
  /\*\*\
  \* Abstract interface for API response structures.\
  \*/\
  export interface BaseResponse {}\
  \
  /\*\*\
  \* Defines a standard structure for API resources/DTOs with a unique
  identifier.\
  \*/\
  export interface BaseResource {\
  /\*\*\
  \* The unique identifier for the resource.\
  \*/\
  id: number;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(shared): add base response and resource
  interfaces.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Base Assembler

-   Generate Base Assembler

  -----------------------------------------------------------------------
  ng g interface shared/infrastructure/BaseAssembler
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace base-assembler.ts with the following code:

  -----------------------------------------------------------------------
  import {BaseResource, BaseResponse} from \'./base-response\';\
  import {BaseEntity} from \'./base-entity\';\
  \
  /\*\*\
  \* Defines a contract for assembler classes that convert between
  entities, resources, and API responses.\
  \*\
  \* \@template TEntity - The entity type (e.g., Course), must\
  \* \@template TResource - The resource type, must extend BaseResource.\
  \* \@template TResponse - The response type, must extend BaseResponse.\
  \*/\
  export interface BaseAssembler\<TEntity extends BaseEntity, TResource
  extends BaseResource, TResponse extends BaseResponse\> {\
  /\*\*\
  \* Converts a resource to an entity.\
  \* \@param resource - The resource to convert.\
  \* \@returns The converted entity.\
  \*/\
  toEntityFromResource(resource: TResource): TEntity;\
  \
  /\*\*\
  \* Converts an entity to a resource.\
  \* \@param entity - The entity to convert.\
  \* \@returns The converted resource.\
  \*/\
  toResourceFromEntity(entity: TEntity): TResource;\
  \
  /\*\*\
  \* Converts an API response to an array of entities.\
  \* \@param response - The API response containing entities.\
  \* \@returns An array of entities.\
  \*/\
  toEntitiesFromResponse(response: TResponse): TEntity\[\];\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(shared): add base assembler interface for
  entity-resource conversions.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create BaseApi Endpoint

-   Generate BaseApi Endpoint

  -----------------------------------------------------------------------
  ng g class shared/infrastructure/BaseApiEndpoint \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace base-api-endpoint.ts with the following code:

  -----------------------------------------------------------------------
  import {HttpClient, HttpErrorResponse} from \'@angular/common/http\';\
  import {Observable, throwError} from \'rxjs\';\
  import {catchError, map} from \'rxjs/operators\';\
  import {BaseEntity} from \'./base-entity\';\
  import {BaseResource, BaseResponse} from \'./base-response\';\
  import {BaseAssembler} from \'./base-assembler\';\
  \
  /\*\*\
  \* Base class for API endpoint operations with generic CRUD
  functionality.\
  \*\
  \* \@template TEntity - The entity type, which must extend BaseEntity.\
  \* \@template TResource - The resource type, must extend BaseResource.\
  \* \@template TResponse - The response type, must extend BaseResponse.\
  \* \@template TAssembler - The assembler type implementing
  BaseAssembler with matching generics.\
  \*/\
  export abstract class BaseApiEndpoint\<\
  TEntity extends BaseEntity,\
  TResource extends BaseResource,\
  TResponse extends BaseResponse,\
  TAssembler extends BaseAssembler\<TEntity, TResource, TResponse\>\
  \> {\
  constructor(\
  protected http: HttpClient,\
  protected endpointUrl: string,\
  protected assembler: TAssembler\
  ) {}\
  \
  /\*\*\
  \* Retrieves all entities from the API, handling both response objects
  and arrays.\
  \* \@returns An Observable for an array of entities.\
  \*/\
  getAll(): Observable\<TEntity\[\]\> {\
  return this.http.get\<TResponse \|
  TResource\[\]\>(this.endpointUrl).pipe(\
  map(response =\> {\
  console.log(response);\
  if (Array.isArray(response)) {\
  return response.map(resource =\>
  this.assembler.toEntityFromResource(resource));\
  }\
  return this.assembler.toEntitiesFromResponse(response as TResponse);\
  }),\
  catchError(this.handleError(\'Failed to fetch entities\'))\
  );\
  }\
  \
  /\*\*\
  \* Retrieves a single entity by ID.\
  \* \@param id - The ID of the entity.\
  \* \@returns An Observable of the entity.\
  \*/\
  getById(id: number): Observable\<TEntity\> {\
  return
  this.http.get\<TResource\>(\`\${this.endpointUrl}/\${id}\`).pipe(\
  map(resource =\> this.assembler.toEntityFromResource(resource)),\
  catchError(this.handleError(\'Failed to fetch entity\'))\
  );\
  }\
  \
  /\*\*\
  \* Creates a new entity.\
  \* \@param entity - The entity to create.\
  \* \@returns An Observable of the created entity.\
  \*/\
  create(entity: TEntity): Observable\<TEntity\> {\
  const resource = this.assembler.toResourceFromEntity(entity);\
  return this.http.post\<TResource\>(this.endpointUrl, resource).pipe(\
  map(created =\> this.assembler.toEntityFromResource(created)),\
  catchError(this.handleError(\'Failed to create entity\'))\
  );\
  }\
  \
  /\*\*\
  \* Updates an existing entity.\
  \* \@param entity - The entity to update.\
  \* \@param id - The ID of the entity.\
  \* \@returns An Observable of the updated entity.\
  \*/\
  update(entity: TEntity, id: number): Observable\<TEntity\> {\
  const resource = this.assembler.toResourceFromEntity(entity);\
  return this.http.put\<TResource\>(\`\${this.endpointUrl}/\${id}\`,
  resource).pipe(\
  map(updated =\> this.assembler.toEntityFromResource(updated)),\
  catchError(this.handleError(\'Failed to update entity\'))\
  );\
  }\
  \
  /\*\*\
  \* Deletes an entity by ID.\
  \* \@param id - The ID of the entity to delete.\
  \* \@returns An Observable of void.\
  \*/\
  delete(id: number): Observable\<void\> {\
  return this.http.delete\<void\>(\`\${this.endpointUrl}/\${id}\`).pipe(\
  catchError(this.handleError(\'Failed to delete entity\'))\
  );\
  }\
  \
  /\*\*\
  \* Handles HTTP errors and returns a user-friendly error message.\
  \* \@param operation - The operation that failed.\
  \* \@returns A function that transforms an error into an Observable.\
  \*/\
  protected handleError(operation: string) {\
  return (error: HttpErrorResponse): Observable\<never\> =\> {\
  let errorMessage = operation;\
  if (error.status === 404) {\
  errorMessage = \`\${operation}: Resource not found\`;\
  } else if (error.error instanceof ErrorEvent) {\
  errorMessage = \`\${operation}: \${error.error.message}\`;\
  } else {\
  errorMessage = \`\${operation}: \${error.statusText \|\| \'Unexpected
  error\'}\`;\
  }\
  return throwError(() =\> new Error(errorMessage));\
  };\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(shared): add base API endpoint for generic crud
  operations.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create BaseApi

-   Generate BaseApi

  -----------------------------------------------------------------------
  ng g class shared/infrastructure/BaseApi \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace base-api.ts with the following code:

  -----------------------------------------------------------------------
  /\*\*\
  \* Abstract base class for API services managing multiple endpoints
  within a bounded context.\
  \*/\
  export abstract class BaseApi {\
  // No methods defined; child classes will compose endpoint instances\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(shared): add abstract base api class for api
  endpoint composition.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Categories Response

-   Generate Categories Response

  -----------------------------------------------------------------------
  ng g interface learning/infrastructure/CategoriesResponse
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace categories-response.ts with the following code:

  -----------------------------------------------------------------------
  import {BaseResource, BaseResponse} from
  \'../../shared/infrastructure/base-response\';\
  \
  /\*\*\
  \* Represents the API resource/DTO for a category.\
  \*/\
  export interface CategoryResource extends BaseResource {\
  /\*\*\
  \* The unique identifier for the category.\
  \*/\
  id: number;\
  \
  /\*\*\
  \* The name of the category.\
  \*/\
  name: string;\
  \
  }\
  \
  /\*\*\
  \* Represents the API response structure for a list of categories.\
  \*/\
  export interface CategoriesResponse extends BaseResponse {\
  /\*\*\
  \* The list of categories returned by the API.\
  \*/\
  categories: CategoryResource\[\];\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add categories response resource for
  api integration.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Courses Response

-   Generate Courses Response

  -----------------------------------------------------------------------
  ng g interface learning/infrastructure/CoursesResponse
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace courses-response.ts with the following code:

  -----------------------------------------------------------------------
  import {BaseResource, BaseResponse} from
  \'../../shared/infrastructure/base-response\';\
  \
  /\*\*\
  \* Represents a single course resource returned from the API.\
  \*\
  \* \@remarks\
  \* This interface extends {@link BaseResource} and includes the core
  properties of a course.\
  \*\
  \* \@property id - Unique identifier for the course.\
  \* \@property title - Title of the course.\
  \* \@property description - Description of the course.\
  \*/\
  export interface CourseResource extends BaseResource {\
  /\*\*\
  \* Unique identifier for the course.\
  \*/\
  id: number;\
  /\*\*\
  \* Title of the course.\
  \*/\
  title: string;\
  /\*\*\
  \* Description of the course.\
  \*/\
  description: string;\
  \
  /\*\*\
  \* Identifier for the category this course belongs to.\
  \*/\
  categoryId: number;\
  }\
  \
  /\*\*\
  \* Represents the response structure for a list of courses from the
  API.\
  \*\
  \* \@remarks\
  \* This interface extends {@link BaseResponse} and contains an array of
  {@link CourseResource} objects.\
  \*\
  \* \@property courses - Array of course resources included in the
  response.\
  \*\
  \* \@example\
  \* \`\`\`typescript\
  \* const response: CoursesResponse = {\
  \* status: \'success\',\
  \* courses: \[\
  \* { id: 1, title: \'Intro to TypeScript\', description: \'Learn TS\',
  \... },\
  \* { id: 2, title: \'Advanced Angular\', description: \'Deep dive\',
  \... }\
  \* \]\
  \* };\
  \* \`\`\`\
  \*/\
  export interface CoursesResponse extends BaseResponse {\
  /\*\*\
  \* Array of course resources included in the response.\
  \*/\
  courses: CourseResource\[\];\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add courses response resource for api
  integration.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Category Assembler

-   Generate Category Assembler

  -----------------------------------------------------------------------
  ng g class learning/infrastructure/CategoryAssembler \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace category-assembler.ts with the following code:

  -----------------------------------------------------------------------
  import {BaseAssembler} from
  \'../../shared/infrastructure/base-assembler\';\
  import {Category} from \'../domain/model/category.entity\';\
  import {CategoriesResponse, CategoryResource} from
  \'./categories-response\';\
  \
  /\*\*\
  \* Assembler for converting between Category entities, CategoryResource
  resources, and CategoriesResponse.\
  \*/\
  export class CategoryAssembler implements BaseAssembler\<Category,
  CategoryResource, CategoriesResponse\> {\
  \
  /\*\*\
  \* Converts a CategoriesResponse to an array of Category entities.\
  \* \@param response - The API response containing categories.\
  \* \@returns An array of Category entities.\
  \*/\
  toEntitiesFromResponse(response: CategoriesResponse): Category\[\] {\
  return response.categories.map(resource =\>
  this.toEntityFromResource(resource as CategoryResource));\
  }\
  \
  /\*\*\
  \* Converts a CategoryResource to a Category entity.\
  \* \@param resource - The resource to convert.\
  \* \@returns The converted Category entity.\
  \*/\
  toEntityFromResource(resource: CategoryResource): Category {\
  return new Category({\
  id: resource.id,\
  name: resource.name\
  });\
  }\
  \
  /\*\*\
  \* Converts a Category entity to a CategoryResource.\
  \* \@param entity - The entity to convert.\
  \* \@returns The converted CategoryResource.\
  \*/\
  toResourceFromEntity(entity: Category): CategoryResource {\
  return {\
  id: entity.id,\
  name: entity.name\
  } as CategoryResource;\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): implement category assembler for
  entity-resource conversions.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create Course Assembler

-   Generate Course Assembler

  -----------------------------------------------------------------------
  ng g class learning/infrastructure/CourseAssembler \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace course-assembler.ts with the following code:

  -----------------------------------------------------------------------
  import {CourseResource, CoursesResponse} from \'./courses-response\';\
  import {Course} from \'../domain/model/course.entity\';\
  import {BaseAssembler} from
  \'../../shared/infrastructure/base-assembler\';\
  \
  /\*\*\
  \* Assembler for converting between Course entities, CourseResource
  resources, and CoursesResponse.\
  \*/\
  export class CourseAssembler implements BaseAssembler\<Course,
  CourseResource, CoursesResponse\> {\
  /\*\*\
  \* Converts a CoursesResponse to an array of Course entities.\
  \* \@param response - The API response containing courses.\
  \* \@returns An array of Course entities.\
  \*/\
  toEntitiesFromResponse(response: CoursesResponse): Course\[\] {\
  console.log(response);\
  return response.courses.map(resource =\>
  this.toEntityFromResource(resource as CourseResource));\
  }\
  \
  /\*\*\
  \* Converts a CourseResource to a Course entity.\
  \* \@param resource - The resource to convert.\
  \* \@returns The converted Course entity.\
  \*/\
  toEntityFromResource(resource: CourseResource): Course {\
  return new Course({\
  id: resource.id,\
  title: resource.title,\
  description: resource.description,\
  categoryId: resource.categoryId\
  });\
  }\
  \
  /\*\*\
  \* Converts a Course entity to a CourseResource.\
  \* \@param entity - The entity to convert.\
  \* \@returns The converted CourseResource.\
  \*/\
  toResourceFromEntity(entity: Course): CourseResource {\
  return {\
  id: entity.id,\
  title: entity.title,\
  description: entity.description\
  } as CourseResource;\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): implement course assembler for
  entity-resource conversions.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create CategoriesApi Endpoint

-   Generate CategoriesApi Endpoint

  -----------------------------------------------------------------------
  ng g class learning/infrastructure/CategoriesApiEndpoint \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace categories-api-endpoint.ts with the following code:

  -------------------------------------------------------------------------------------------------------
  import {BaseApiEndpoint} from \'../../shared/infrastructure/base-api-endpoint\';\
  import {Category} from \'../domain/model/category.entity\';\
  import {CategoriesResponse, CategoryResource} from \'./categories-response\';\
  import {CategoryAssembler} from \'./category-assembler\';\
  import {HttpClient} from \'@angular/common/http\';\
  import {environment} from \'../../../environments/environment\';\
  \
  /\*\*\
  \* API endpoint for managing categories.\
  \*/\
  export class CategoriesApiEndpoint extends BaseApiEndpoint\<Category, CategoryResource,
  CategoriesResponse, CategoryAssembler\> {\
  /\*\*\
  \* Creates an instance of CategoriesApiEndpoint.\
  \* \@param http - The HttpClient to be used for making API requests.\
  \*/\
  constructor(http: HttpClient) {\
  super(http,
  \`\${environment.platformProviderApiBaseUrl}\${environment.platformProviderCategoriesEndpointPath}\`,
  new CategoryAssembler());\
  }\
  }
  -------------------------------------------------------------------------------------------------------

  -------------------------------------------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add categories api endpoint for
  category management.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create CoursesApi Endpoint

-   Generate CoursesApi Endpoint

  -----------------------------------------------------------------------
  ng g class learning/infrastructure/CoursesApiEndpoint \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace courses-api-endpoint.ts with the following code:

  ----------------------------------------------------------------------------------------------------
  import {BaseApiEndpoint} from \'../../shared/infrastructure/base-api-endpoint\';\
  import {Course} from \'../domain/model/course.entity\';\
  import {CourseResource, CoursesResponse} from \'./courses-response\';\
  import {CourseAssembler} from \'./course-assembler\';\
  import {HttpClient} from \'@angular/common/http\';\
  import {environment} from \'../../../environments/environment\';\
  \
  /\*\*\
  \* API endpoint for managing courses.\
  \*/\
  export class CoursesApiEndpoint extends BaseApiEndpoint\<Course, CourseResource, CoursesResponse,
  CourseAssembler\> {\
  constructor(http: HttpClient) {\
  super(http,
  \`\${environment.platformProviderApiBaseUrl}\${environment.platformProviderCoursesEndpointPath}\`,
  new CourseAssembler());\
  }\
  }
  ----------------------------------------------------------------------------------------------------

  ----------------------------------------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add courses api endpoint for course
  management.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create LearningApi

-   Generate LearningApi

  -----------------------------------------------------------------------
  ng g class learning/infrastructure/LearningApi \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace learning-api.ts with the following code:

  -----------------------------------------------------------------------
  import {Injectable} from \'@angular/core\';\
  import {BaseApi} from \'../../shared/infrastructure/base-api\';\
  import {Course} from \'../domain/model/course.entity\';\
  import {Category} from \'../domain/model/category.entity\';\
  import {HttpClient} from \'@angular/common/http\';\
  import {CoursesApiEndpoint} from \'./courses-api-endpoint\';\
  import {CategoriesApiEndpoint} from \'./categories-api-endpoint\';\
  import {Observable} from \'rxjs\';\
  \
  /\*\*\
  \* API service for managing endpoints in the learning context (courses
  and categories).\
  \*/\
  \@Injectable({providedIn: \'root\'})\
  export class LearningApi extends BaseApi {\
  private readonly coursesEndpoint: CoursesApiEndpoint;\
  private readonly categoriesEndpoint: CategoriesApiEndpoint;\
  \
  constructor(http: HttpClient) {\
  super();\
  this.coursesEndpoint = new CoursesApiEndpoint(http);\
  this.categoriesEndpoint = new CategoriesApiEndpoint(http);\
  }\
  \
  /\*\*\
  \* Retrieves all courses from the API.\
  \* \@returns An Observable for an array of Course objects.\
  \*/\
  getCourses(): Observable\<Course\[\]\> {\
  return this.coursesEndpoint.getAll();\
  }\
  \
  /\*\*\
  \* Retrieves a single course by ID.\
  \* \@param id - The ID of the course.\
  \* \@returns An Observable of the Course object.\
  \*/\
  getCourse(id: number): Observable\<Course\> {\
  return this.coursesEndpoint.getById(id);\
  }\
  \
  /\*\*\
  \* Creates a new course.\
  \* \@param course - The course to create.\
  \* \@returns An Observable of the created Course object.\
  \*/\
  createCourse(course: Course): Observable\<Course\> {\
  return this.coursesEndpoint.create(course);\
  }\
  \
  /\*\*\
  \* Updates an existing course.\
  \* \@param course - The course to update.\
  \* \@returns An Observable of the updated Course object.\
  \*/\
  updateCourse(course: Course): Observable\<Course\> {\
  return this.coursesEndpoint.update(course, course.id);\
  }\
  \
  /\*\*\
  \* Deletes a course by ID.\
  \* \@param id - The ID of the course to delete.\
  \* \@returns An Observable of void.\
  \*/\
  deleteCourse(id: number): Observable\<void\> {\
  return this.coursesEndpoint.delete(id);\
  }\
  \
  /\*\*\
  \* Retrieves all categories from the API.\
  \* \@returns An Observable for an array of Category objects.\
  \*/\
  getCategories(): Observable\<Category\[\]\> {\
  return this.categoriesEndpoint.getAll();\
  }\
  \
  /\*\*\
  \* Retrieves a single category by ID.\
  \* \@param id - The ID of the category.\
  \* \@returns An Observable of the Category object.\
  \*/\
  getCategory(id: number): Observable\<Category\> {\
  return this.categoriesEndpoint.getById(id);\
  }\
  \
  /\*\*\
  \* Creates a new category.\
  \* \@param category - The category to create.\
  \* \@returns An Observable of the created Category object.\
  \*/\
  createCategory(category: Category): Observable\<Category\> {\
  return this.categoriesEndpoint.create(category);\
  }\
  \
  /\*\*\
  \* Updates an existing category.\
  \* \@param category - The category to update.\
  \* \@returns An Observable of the updated Category object.\
  \*/\
  updateCategory(category: Category): Observable\<Category\> {\
  return this.categoriesEndpoint.update(category, category.id);\
  }\
  \
  /\*\*\
  \* Deletes a category by ID.\
  \* \@param id - The ID of the category to delete.\
  \* \@returns An Observable of void.\
  \*/\
  deleteCategory(id: number): Observable\<void\> {\
  return this.categoriesEndpoint.delete(id);\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add learning api service for courses
  and categories management.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create LearningStore

-   Generate LearningStore

  -----------------------------------------------------------------------
  ng g class learning/application/Learning \--type=store \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace learning-store.ts with the following code:

  ------------------------------------------------------------------------------
  import {computed, Injectable, Signal, signal} from \'@angular/core\';\
  import {Course} from \'../domain/model/course.entity\';\
  import {Category} from \'../domain/model/category.entity\';\
  import {LearningApi} from \'../infrastructure/learning-api\';\
  import {takeUntilDestroyed} from \'@angular/core/rxjs-interop\';\
  import {retry} from \'rxjs\';\
  \
  /\*\*\
  \* State management store for courses and categories using Angular signals.\
  \*/\
  \@Injectable({\
  providedIn: \'root\'\
  })\
  export class LearningStore {\
  readonly courseCount = computed(() =\> this.courses().length);\
  readonly categoryCount = computed(() =\> this.categories().length);\
  private readonly coursesSignal = signal\<Course\[\]\>(\[\]);\
  readonly courses = this.coursesSignal.asReadonly();\
  private readonly categoriesSignal = signal\<Category\[\]\>(\[\]);\
  readonly categories = this.categoriesSignal.asReadonly();\
  private readonly loadingSignal = signal\<boolean\>(false);\
  readonly loading = this.loadingSignal.asReadonly();\
  private readonly errorSignal = signal\<string \| null\>(null);\
  readonly error = this.errorSignal.asReadonly();\
  \
  constructor(private learningApi: LearningApi) {\
  this.loadCategories();\
  this.loadCourses();\
  }\
  \
  /\*\*\
  \* Retrieves a category by its ID as a signal.\
  \* \@param id - The ID of the category.\
  \* \@returns A Signal containing the Category object or undefined if not
  found.\
  \*/\
  getCategoryById(id: number \| null \| undefined): Signal\<Category \|
  undefined\> {\
  return computed(() =\> id ? this.categories().find(c =\> c.id === id) :
  undefined);\
  }\
  \
  /\*\*\
  \* Adds a new course.\
  \* \@param course - The course to add.\
  \*/\
  addCourse(course: Course): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.createCourse(course).pipe(retry(2)).subscribe({\
  next: createdCourse =\> {\
  //this.assignCategoryToCourse(createdCourse);\
  this.coursesSignal.update(courses =\> \[\...courses, createdCourse\]);\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to create course\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Updates an existing course.\
  \* \@param updatedCourse - The course to update.\
  \*/\
  updateCourse(updatedCourse: Course): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.updateCourse(updatedCourse).pipe(retry(2)).subscribe({\
  next: course =\> {\
  //this.assignCategoryToCourse(course);\
  this.coursesSignal.update(courses =\>\
  courses.map(c =\> c.id === course.id ? course : c)\
  );\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to update course\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Deletes a course by ID.\
  \* \@param id - The ID of the course to delete.\
  \*/\
  deleteCourse(id: number): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.deleteCourse(id).pipe(retry(2)).subscribe({\
  next: () =\> {\
  this.coursesSignal.update(courses =\> courses.filter(c =\> c.id !== id));\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to delete course\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Adds a new category.\
  \* \@param category - The category to add.\
  \*/\
  addCategory(category: Category): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.createCategory(category).pipe(retry(2)).subscribe({\
  next: createdCategory =\> {\
  this.categoriesSignal.update(categories =\> \[\...categories,
  createdCategory\]);\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to create category\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Updates an existing category.\
  \* \@param updatedCategory - The category to update.\
  \*/\
  updateCategory(updatedCategory: Category): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.updateCategory(updatedCategory).pipe(retry(2)).subscribe({\
  next: category =\> {\
  this.categoriesSignal.update(categories =\>\
  categories.map(c =\> c.id === category.id ? category : c)\
  );\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to update category\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Deletes a category by ID.\
  \* \@param id - The ID of the category to delete.\
  \*/\
  deleteCategory(id: number): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.deleteCategory(id).pipe(retry(2)).subscribe({\
  next: () =\> {\
  this.categoriesSignal.update(categories =\> categories.filter(c =\> c.id !==
  id));\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to delete category\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Loads all courses from the API.\
  \*/\
  private loadCourses(): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.getCourses().pipe(takeUntilDestroyed()).subscribe({\
  next: courses =\> {\
  console.log(courses);\
  this.coursesSignal.set(courses);\
  this.loadingSignal.set(false);\
  //this.assignCategoriesToCourses();\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to load courses\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Loads all categories from the API.\
  \*/\
  private loadCategories(): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.getCategories().pipe(takeUntilDestroyed()).subscribe({\
  next: categories =\> {\
  this.categoriesSignal.set(categories);\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to load categories\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  private assignCategoriesToCourses(): void {\
  this.coursesSignal.update(courses =\> courses.map(course =\>
  this.assignCategoryToCourse(course)));\
  }\
  \
  private assignCategoryToCourse(course: Course): Course {\
  const categoryId = course.categoryId ?? 0;\
  const category = categoryId ? this.categories().find(cat =\> cat.id ===
  categoryId) ?? null : null;\
  return {\...course, category} as Course;\
  }\
  \
  /\*\*\
  \* Formats error messages for user-friendly display.\
  \* \@param error - The error object.\
  \* \@param fallback - The fallback error message.\
  \* \@returns A formatted error message.\
  \*/\
  private formatError(error: any, fallback: string): string {\
  if (error instanceof Error) {\
  return error.message.includes(\'Resource not found\') ? \`\${fallback}: Not
  found\` : error.message;\
  }\
  return fallback;\
  }\
  }
  ------------------------------------------------------------------------------

  ------------------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add learning store for state
  management.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create CategoryForm Component

-   Generate CategoryForm Component

  -----------------------------------------------------------------------
  ng g c learning/presentation/views/CategoryForm \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace category-form.ts with the following code:

  -----------------------------------------------------------------------
  import {Component, inject} from \'@angular/core\';\
  import {FormBuilder, FormControl, ReactiveFormsModule, Validators} from
  \'@angular/forms\';\
  import {ActivatedRoute, Router} from \'@angular/router\';\
  import {LearningStore} from \'../../../application/learning.store\';\
  import {Category} from \'../../../domain/model/category.entity\';\
  import {MatButtonModule} from \'@angular/material/button\';\
  import {MatFormFieldModule} from \'@angular/material/form-field\';\
  import {MatInputModule} from \'@angular/material/input\';\
  \
  \@Component({\
  selector: \'app-category-form\',\
  imports: \[MatFormFieldModule, MatInputModule, MatButtonModule,
  ReactiveFormsModule\],\
  templateUrl: \'./category-form.html\',\
  styleUrl: \'./category-form.css\'\
  })\
  export class CategoryForm {\
  private fb = inject(FormBuilder);\
  private route = inject(ActivatedRoute);\
  private router = inject(Router);\
  private store = inject(LearningStore);\
  \
  form = this.fb.group({\
  name: new FormControl\<string\>(\'\', { nonNullable: true, validators:
  \[Validators.required\] })\
  });\
  isEdit = false;\
  categoryId: number \| null = null;\
  \
  constructor() {\
  this.route.params.subscribe(params =\> {\
  this.categoryId = params\[\'id\'\] ? +params\[\'id\'\] : null;\
  this.isEdit = !!this.categoryId;\
  if (this.isEdit) {\
  const category = this.store.getCategoryById(this.categoryId)();\
  if (category) {\
  this.form.patchValue({ name: category.name });\
  }\
  }\
  });\
  }\
  \
  submit() {\
  if (this.form.invalid) return;\
  \
  const category: Category = new Category({\
  id: this.categoryId ?? 0,\
  name: this.form.value.name!\
  });\
  \
  if (this.isEdit) {\
  this.store.updateCategory(category);\
  } else {\
  this.store.addCategory(category);\
  }\
  \
  this.router.navigate(\[\'learning/categories\'\]).then();\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace category-form.html with the following code:

  -----------------------------------------------------------------------
  \<**form** \[formGroup\]=\"form\" (ngSubmit)=\"submit()\"\>\
  \<**mat-form-field**\>\
  \<**mat-label**\>Name\</**mat-label**\>\
  \<**input** matInput formControlName=\"name\" required\>\
  \@if (form.get(\'name\')!.touched &&
  form.get(\'name\')!.hasError(\'required\')) {\
  \<**mat-error**\>Name is required\</**mat-error**\>\
  }\
  \</**mat-form-field**\>\
  \
  \<**button** mat-raised-button color=\"primary\" type=\"submit\"
  \[disabled\]=\"form.invalid\"\>\
  {{ isEdit ? \'Update\' : \'Add\' }} Category\
  \</**button**\>\
  \</**form**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace category-form.css with the following code:

  -----------------------------------------------------------------------
  form {\
  display: flex;\
  flex-direction: column;\
  gap: 16px;\
  max-width: 600px;\
  margin: 16px;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add category form component for
  creating and editing categories.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create CategoryList Component

-   Generate CategoryList Component

  -----------------------------------------------------------------------
  ng g c learning/presentation/views/CategoryList \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace category-list.ts with the following code:

  -----------------------------------------------------------------------
  import {Component, inject} from \'@angular/core\';\
  import {Router} from \'@angular/router\';\
  import {MatButtonModule} from \'@angular/material/button\';\
  import {MatTableModule} from \'@angular/material/table\';\
  import {LearningStore} from \'../../../application/learning.store\';\
  import {MatError} from \'@angular/material/form-field\';\
  import {MatProgressSpinner} from
  \'@angular/material/progress-spinner\';\
  \
  \@Component({\
  selector: \'app-category-list\',\
  imports: \[MatTableModule, MatButtonModule, MatError,
  MatProgressSpinner\],\
  templateUrl: \'./category-list.html\',\
  styleUrl: \'./category-list.css\'\
  })\
  export class CategoryList {\
  readonly store = inject(LearningStore);\
  protected router = inject(Router);\
  \
  displayedColumns: string\[\] = \[\'id\', \'name\', \'actions\'\];\
  \
  editCategory(id: number) {\
  this.router.navigate(\[\'learning/categories/edit\', id\]).then();\
  }\
  \
  deleteCategory(id: number) {\
  this.store.deleteCategory(id);\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace category-list.html with the following code:

  -----------------------------------------------------------------------
  \@if (store.loading()) {\
  \<**mat-spinner** diameter=\"40\"\>\</**mat-spinner**\>\
  }\
  \@if (store.error()) {\
  \<**mat-error**\>{{ store.error() }}\</**mat-error**\>\
  }\
  \<**table** mat-table \[dataSource\]=\"store.categories()\"
  class=\"mat-elevation-z8\"\>\
  \<!\-- ID Column \--\>\
  \<**ng-container** matColumnDef=\"id\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef\> ID \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let category\"\> {{ category.id }}
  \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Name Column \--\>\
  \<**ng-container** matColumnDef=\"name\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef\> Name \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let category\"\> {{ category.name }}
  \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Actions Column \--\>\
  \<**ng-container** matColumnDef=\"actions\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef\> Actions \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let category\"\>\
  \<**button** mat-button
  (click)=\"editCategory(category.id)\"\>Edit\</**button**\>\
  \<**button** mat-button
  (click)=\"deleteCategory(category.id)\"\>Delete\</**button**\>\
  \</**td**\>\
  \</**ng-container**\>\
  \
  \<**tr** mat-header-row
  \*matHeaderRowDef=\"displayedColumns\"\>\</**tr**\>\
  \<**tr** mat-row \*matRowDef=\"let row; columns:
  displayedColumns;\"\>\</**tr**\>\
  \</**table**\>\
  \
  \<**button** mat-raised-button color=\"primary\"
  (click)=\"router.navigate(\[\'learning/categories/new\'\])\"\>Add
  Category\</**button**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace category-list.css with the following code:

  -----------------------------------------------------------------------
  .mat-table {\
  width: 100%;\
  margin-bottom: 16px;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add category list component for
  displaying and managing categories.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create CourseForm Component

-   Generate CourseForm Component

  -----------------------------------------------------------------------
  ng g c learning/presentation/views/CourseForm \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace course-form.ts with the following code:

  -----------------------------------------------------------------------
  import {Component, inject} from \'@angular/core\';\
  import {FormBuilder, FormControl, ReactiveFormsModule, Validators} from
  \'@angular/forms\';\
  import {ActivatedRoute, Router} from \'@angular/router\';\
  import {LearningStore} from \'../../../application/learning.store\';\
  import {Course} from \'../../../domain/model/course.entity\';\
  import {Category} from \'../../../domain/model/category.entity\';\
  import {MatFormFieldModule} from \'@angular/material/form-field\';\
  import {MatSelectModule} from \'@angular/material/select\';\
  import {MatButtonModule} from \'@angular/material/button\';\
  import {MatInput} from \'@angular/material/input\';\
  \
  \@Component({\
  selector: \'app-course-form\',\
  imports: \[\
  ReactiveFormsModule,\
  MatFormFieldModule,\
  MatSelectModule,\
  MatButtonModule,\
  MatInput\
  \],\
  templateUrl: \'./course-form.html\',\
  styleUrl: \'./course-form.css\'\
  })\
  export class CourseForm {\
  private fb = inject(FormBuilder);\
  private route = inject(ActivatedRoute);\
  private router = inject(Router);\
  private store = inject(LearningStore);\
  \
  form = this.fb.group({\
  title: new FormControl\<string\>(\'\', { nonNullable: true, validators:
  \[Validators.required\] }),\
  description: new FormControl\<string\>(\'\', { nonNullable: true,
  validators: \[Validators.required\] }),\
  categoryId: new FormControl\<number \| null\>(null)\
  });\
  categories = this.store.categories;\
  isEdit = false;\
  courseId: number \| null = null;\
  \
  constructor() {\
  this.route.params.subscribe(params =\> {\
  this.courseId = params\[\'id\'\] ? +params\[\'id\'\] : null;\
  this.isEdit = !!this.courseId;\
  if (this.isEdit) {\
  const course = this.store.courses().find(c =\> c.id ===
  this.courseId);\
  if (course) {\
  this.form.patchValue({\
  title: course.title,\
  description: course.description,\
  categoryId: course.categoryId\
  });\
  }\
  }\
  });\
  }\
  \
  submit() {\
  if (this.form.invalid) return;\
  const category: Category \| null =
  this.store.getCategoryById(this.form.value.categoryId)() ?? null;\
  const course: Course = new Course({\
  id: this.courseId ?? 0,\
  title: this.form.value.title!,\
  description: this.form.value.description!,\
  categoryId: this.form.value.categoryId ?? 0,\
  category: category ?? null\
  });\
  \
  if (this.isEdit) {\
  this.store.updateCourse(course);\
  } else {\
  this.store.addCourse(course);\
  }\
  \
  this.router.navigate(\[\'learning/courses\'\]).then();\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace course-form.html with the following code:

  -----------------------------------------------------------------------
  \<**form** \[formGroup\]=\"form\" (ngSubmit)=\"submit()\"\>\
  \<**mat-form-field**\>\
  \<**mat-label**\>Title\</**mat-label**\>\
  \<**input** matInput formControlName=\"title\" required\>\
  \@if (form.get(\'title\')?.touched &&
  form.get(\'title\')!.hasError(\'required\')) {\
  \<**mat-error**\>Title is required\</**mat-error**\>\
  }\
  \</**mat-form-field**\>\
  \
  \<**mat-form-field**\>\
  \<**mat-label**\>Description\</**mat-label**\>\
  \<**input** matInput formControlName=\"description\" required\>\
  \@if (form.get(\'description\')?.touched &&
  form.get(\'description\')!.hasError(\'required\')) {\
  \<**mat-error**\>Description is required\</**mat-error**\>\
  }\
  \</**mat-form-field**\>\
  \
  \<**mat-form-field**\>\
  \<**mat-label**\>Category\</**mat-label**\>\
  \<**mat-select** formControlName=\"categoryId\"\>\
  \<**mat-option** \[value\]=\"null\"\>None\</**mat-option**\>\
  \@for (category of categories(); track category.id) {\
  \<**mat-option** \[value\]=\"category.id\"\>{{ category.name
  }}\</**mat-option**\>\
  }\
  \</**mat-select**\>\
  \</**mat-form-field**\>\
  \
  \<**button** mat-raised-button color=\"primary\" type=\"submit\"
  \[disabled\]=\"form.invalid\"\>\
  {{ isEdit ? \'Update\' : \'Add\' }} Course\
  \</**button**\>\
  \</**form**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace course-form.css with the following code:

  -----------------------------------------------------------------------
  form {\
  display: flex;\
  flex-direction: column;\
  gap: 16px;\
  max-width: 600px;\
  margin: 16px;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add course form component for creating
  and editing courses.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create CourseList Component

-   Generate CourseList Component

  -----------------------------------------------------------------------
  ng g c learning/presentation/views/CourseList \--skip-tests
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace course-list.ts with the following code:

  -----------------------------------------------------------------------
  import {Component, inject} from \'@angular/core\';\
  import {LearningStore} from \'../../../application/learning.store\';\
  import {Router} from \'@angular/router\';\
  import {MatError} from \'@angular/material/form-field\';\
  import {\
  MatCell,\
  MatCellDef,\
  MatColumnDef,\
  MatHeaderCell,\
  MatHeaderCellDef,\
  MatHeaderRow,\
  MatHeaderRowDef,\
  MatRow,\
  MatRowDef,\
  MatTable\
  } from \'@angular/material/table\';\
  import {MatButton} from \'@angular/material/button\';\
  import {MatProgressSpinner} from
  \'@angular/material/progress-spinner\';\
  \
  \@Component({\
  selector: \'app-course-list\',\
  imports: \[\
  MatError,\
  MatTable,\
  MatHeaderCellDef,\
  MatCellDef,\
  MatColumnDef,\
  MatHeaderCell,\
  MatCell,\
  MatHeaderRowDef,\
  MatRowDef,\
  MatButton,\
  MatHeaderRow,\
  MatRow,\
  MatProgressSpinner\
  \],\
  templateUrl: \'./course-list.html\',\
  styleUrl: \'./course-list.css\'\
  })\
  export class CourseList {\
  readonly store = inject(LearningStore);\
  protected router = inject(Router);\
  \
  displayedColumns: string\[\] = \[\'id\', \'title\', \'description\',
  \'category\', \'actions\'\];\
  \
  editCourse(id: number) {\
  this.router.navigate(\[\'learning/courses/edit\', id\]).then();\
  }\
  \
  deleteCourse(id: number) {\
  this.store.deleteCourse(id);\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace course-list.html with the following code:

  -----------------------------------------------------------------------
  \@if (store.loading()) {\
  \<**mat-spinner** diameter=\"40\"\>\</**mat-spinner**\>\
  }\
  \@if (store.error()) {\
  \<**mat-error**\>{{ store.error() }}\</**mat-error**\>\
  }\
  \<**table** mat-table \[dataSource\]=\"store.courses()\"
  class=\"mat-elevation-z8\"\>\
  \<!\-- ID Column \--\>\
  \<**ng-container** matColumnDef=\"id\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef\> ID \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let course\"\> {{ course.id }}
  \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Title Column \--\>\
  \<**ng-container** matColumnDef=\"title\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef\> Title \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let course\"\> {{ course.title }}
  \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Description Column \--\>\
  \<**ng-container** matColumnDef=\"description\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef\> Description \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let course\"\> {{ course.description
  }} \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Category Column \--\>\
  \<**ng-container** matColumnDef=\"category\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef\> Category \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let course\"\> {{
  course.category?.name ?? \'None\' }} \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Actions Column \--\>\
  \<**ng-container** matColumnDef=\"actions\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef\> Actions \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let course\"\>\
  \<**button** mat-button
  (click)=\"editCourse(course.id)\"\>Edit\</**button**\>\
  \<**button** mat-button
  (click)=\"deleteCourse(course.id)\"\>Delete\</**button**\>\
  \</**td**\>\
  \</**ng-container**\>\
  \
  \<**tr** mat-header-row
  \*matHeaderRowDef=\"displayedColumns\"\>\</**tr**\>\
  \<**tr** mat-row \*matRowDef=\"let row; columns:
  displayedColumns;\"\>\</**tr**\>\
  \</**table**\>\
  \
  \<**button** mat-raised-button color=\"primary\"
  (click)=\"router.navigate(\[\'learning/courses/new\'\])\"\>Add
  Course\</**button**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace course-list.css with the following code:

  -----------------------------------------------------------------------
  .mat-table {\
  width: 100%;\
  margin-bottom: 16px;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add course list component for
  displaying and managing courses.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Create [learning.routes.ts‎](https://github.com/upc-pre-202520-1asi0729-sandbox/learning-center/commit/7e51d48b8fc9db2c5688c93a0ee7a6b34f22a000#diff-fd762f506ca8f5bd88094db31aaf611a88642c55916a64695a76580c8fcb6d28)

-   Create file src/app/learning/presentation/views/learning.routes.ts

  -----------------------------------------------------------------------
  import {Routes} from \'@angular/router\';\
  \
  const courseList = () =\> import(\'./course-list/course-list\').then(m
  =\> m.CourseList);\
  const courseForm = () =\> import(\'./course-form/course-form\').then(m
  =\> m.CourseForm);\
  const categoryList = () =\>
  import(\'./category-list/category-list\').then(m =\> m.CategoryList);\
  const categoryForm = () =\>
  import(\'./category-form/category-form\').then(m =\> m.CategoryForm);\
  export const learningRoutes: Routes = \[\
  { path: \'courses\', loadComponent: courseList },\
  { path: \'courses/new\', loadComponent: courseForm },\
  { path: \'courses/edit/:id\', loadComponent: courseForm },\
  { path: \'categories\', loadComponent: categoryList },\
  { path: \'categories/new\', loadComponent: categoryForm },\
  { path: \'categories/edit/:id\', loadComponent: categoryForm }\
  \];
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Update app.routes.ts

  ------------------------------------------------------------------------------
  import {Routes} from \'@angular/router\';\
  import {Home} from \'./shared/presentation/views/home/home\';\
  \
  const about = () =\>
  import(\'./shared/presentation/views/about/about\').then(m =\> m.About);\
  const pageNotFound = () =\>
  import(\'./shared/presentation/views/page-not-found/page-not-found\').then(m
  =\> m.PageNotFound);\
  const baseTitle = \'ACME Learning Center\';\
  export const routes: Routes = \[\
  { path: \'home\', component: Home, title: \`\${baseTitle} - Home\` },\
  { path: \'about\', loadComponent: about, title: \`\${baseTitle} - About\` },\
  { path: \'learning\', loadChildren: () =\>
  import(\'./learning/presentation/views/learning.routes\').then(m =\>
  m.learningRoutes)},\
  { path: \'\', redirectTo: \'/home\', pathMatch: \'full\' },\
  { path: \'\*\*\', loadComponent: pageNotFound, title: \`\${baseTitle} - Page
  Not Found\` },\
  \];
  ------------------------------------------------------------------------------

  ------------------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning): add route definitions for courses and
  categories.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update i18n files & Add categories and courses to layout options.

-   Update en.json

  -----------------------------------------------------------------------
  {\
  \"option\": {\
  \"home\": \"Home\",\
  \"about\": \"About Us\",\
  \"categories\": \"Categories\",\
  \"courses\": \"Courses\"\
  },\
  \"about\": {\
  \"title\": \"About us\",\
  \"content\": \"ACME Learning Center is an Education Platform, part of
  ACME Corporation.\"\
  },\
  \"home\": {\
  \"title\": \"Welcome\",\
  \"content\": \"Welcome to ACME Learning Center.\"\
  },\
  \"page-not-found\": {\
  \"title\": \"Page not found\",\
  \"content\": \"The path \<strong\>{{ invalid_path }}\</strong\> is not
  valid.\",\
  \"go-home\": \"Go Home\"\
  },\
  \"footer\": {\
  \"rights\": \"All rights reserved.\",\
  \"powered-by\": \"Powered by\",\
  \"and\": \"and\"\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Update es.json

  -----------------------------------------------------------------------
  {\
  \"option\" : {\
  \"home\": \"Inicio\",\
  \"about\": \"Acerca de\",\
  \"categories\": \"Categorías\",\
  \"courses\": \"Cursos\"\
  },\
  \"about\": {\
  \"title\": \"Acerca de nosotros\",\
  \"content\": \"ACME Learning Center es una plataforma educativa, parte
  de ACME Corporation.\"\
  },\
  \"home\": {\
  \"title\": \"Bienvenido\",\
  \"content\": \"Bienvenido a ACME Learning Center.\"\
  },\
  \"page-not-found\": {\
  \"title\": \"Página no encontrada\",\
  \"content\": \"La ruta \<strong\>{{ invalid_path }}\</strong\> es
  inválida.\",\
  \"go-home\": \"Ir a Inicio\"\
  },\
  \"footer\": {\
  \"rights\": \"Todos los derechos reservados.\",\
  \"powered-by\": \"Desarrollado con\",\
  \"and\": \"y\"\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Update layout.ts

  -----------------------------------------------------------------------
  import {Component} from \'@angular/core\';\
  import {RouterLink, RouterLinkActive, RouterOutlet} from
  \'@angular/router\';\
  import {MatToolbar, MatToolbarRow} from \'@angular/material/toolbar\';\
  import {MatButton} from \'@angular/material/button\';\
  import {TranslatePipe} from \'@ngx-translate/core\';\
  import {LanguageSwitcher} from
  \'../language-switcher/language-switcher\';\
  import {FooterContent} from \'../footer-content/footer-content\';\
  \
  \@Component({\
  selector: \'app-layout\',\
  imports: \[\
  RouterOutlet,\
  RouterLink,\
  MatToolbarRow,\
  MatToolbar,\
  MatButton,\
  RouterLinkActive,\
  TranslatePipe,\
  LanguageSwitcher,\
  FooterContent\
  \],\
  templateUrl: \'./layout.html\',\
  styleUrl: \'./layout.css\'\
  })\
  export class Layout {\
  options = \[\
  {link: \'/home\', label: \'option.home\'},\
  {link: \'/about\', label: \'option.about\'},\
  {link: \'/learning/categories\', label: \'option.categories\'},\
  {link: \'/learning/courses\', label: \'option.courses\'}\
  \]\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(layout): add categories and courses to layout
  options.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update LearningStore

-   Replace learning-store.ts with the following code:

  ------------------------------------------------------------------------------
  import {computed, Injectable, Signal, signal} from \'@angular/core\';\
  import {Course} from \'../domain/model/course.entity\';\
  import {Category} from \'../domain/model/category.entity\';\
  import {LearningApi} from \'../infrastructure/learning-api\';\
  import {takeUntilDestroyed} from \'@angular/core/rxjs-interop\';\
  import {retry} from \'rxjs\';\
  \
  /\*\*\
  \* State management store for courses and categories using Angular signals.\
  \*/\
  \@Injectable({\
  providedIn: \'root\'\
  })\
  export class LearningStore {\
  readonly courseCount = computed(() =\> this.courses().length);\
  readonly categoryCount = computed(() =\> this.categories().length);\
  private readonly coursesSignal = signal\<Course\[\]\>(\[\]);\
  readonly courses = this.coursesSignal.asReadonly();\
  private readonly categoriesSignal = signal\<Category\[\]\>(\[\]);\
  readonly categories = this.categoriesSignal.asReadonly();\
  private readonly loadingSignal = signal\<boolean\>(false);\
  readonly loading = this.loadingSignal.asReadonly();\
  private readonly errorSignal = signal\<string \| null\>(null);\
  readonly error = this.errorSignal.asReadonly();\
  \
  constructor(private learningApi: LearningApi) {\
  this.loadCategories();\
  this.loadCourses();\
  }\
  \
  /\*\*\
  \* Retrieves a category by its ID as a signal.\
  \* \@param id - The ID of the category.\
  \* \@returns A Signal containing the Category object or undefined if not
  found.\
  \*/\
  getCategoryById(id: number): Signal\<Category \| undefined\> {\
  return computed(() =\> id ? this.categories().find(c =\> c.id === id) :
  undefined);\
  }\
  \
  getCourseById(id: number): Signal\<Course \| undefined\> {\
  return computed(() =\> id ? this.courses().find(c =\> c.id === id) :
  undefined);\
  }\
  \
  /\*\*\
  \* Adds a new course.\
  \* \@param course - The course to add.\
  \*/\
  addCourse(course: Course): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.createCourse(course).pipe(retry(2)).subscribe({\
  next: createdCourse =\> {\
  createdCourse = this.assignCategoryToCourse(createdCourse);\
  this.coursesSignal.update(courses =\> \[\...courses, createdCourse\]);\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to create course\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Updates an existing course.\
  \* \@param updatedCourse - The course to update.\
  \*/\
  updateCourse(updatedCourse: Course): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.updateCourse(updatedCourse).pipe(retry(2)).subscribe({\
  next: course =\> {\
  course = this.assignCategoryToCourse(course);\
  this.coursesSignal.update(courses =\>\
  courses.map(c =\> c.id === course.id ? course : c)\
  );\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to update course\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Deletes a course by ID.\
  \* \@param id - The ID of the course to delete.\
  \*/\
  deleteCourse(id: number): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.deleteCourse(id).pipe(retry(2)).subscribe({\
  next: () =\> {\
  this.coursesSignal.update(courses =\> courses.filter(c =\> c.id !== id));\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to delete course\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Adds a new category.\
  \* \@param category - The category to add.\
  \*/\
  addCategory(category: Category): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.createCategory(category).pipe(retry(2)).subscribe({\
  next: createdCategory =\> {\
  this.categoriesSignal.update(categories =\> \[\...categories,
  createdCategory\]);\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to create category\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Updates an existing category.\
  \* \@param updatedCategory - The category to update.\
  \*/\
  updateCategory(updatedCategory: Category): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.updateCategory(updatedCategory).pipe(retry(2)).subscribe({\
  next: category =\> {\
  this.categoriesSignal.update(categories =\>\
  categories.map(c =\> c.id === category.id ? category : c)\
  );\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to update category\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Deletes a category by ID.\
  \* \@param id - The ID of the category to delete.\
  \*/\
  deleteCategory(id: number): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.deleteCategory(id).pipe(retry(2)).subscribe({\
  next: () =\> {\
  this.categoriesSignal.update(categories =\> categories.filter(c =\> c.id !==
  id));\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to delete category\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Loads all courses from the API.\
  \*/\
  private loadCourses(): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.getCourses().pipe(takeUntilDestroyed()).subscribe({\
  next: courses =\> {\
  console.log(courses);\
  this.coursesSignal.set(courses);\
  this.loadingSignal.set(false);\
  this.assignCategoriesToCourses();\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to load courses\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  /\*\*\
  \* Loads all categories from the API.\
  \*/\
  private loadCategories(): void {\
  this.loadingSignal.set(true);\
  this.errorSignal.set(null);\
  this.learningApi.getCategories().pipe(takeUntilDestroyed()).subscribe({\
  next: categories =\> {\
  this.categoriesSignal.set(categories);\
  this.loadingSignal.set(false);\
  },\
  error: err =\> {\
  this.errorSignal.set(this.formatError(err, \'Failed to load categories\'));\
  this.loadingSignal.set(false);\
  }\
  });\
  }\
  \
  private assignCategoriesToCourses(): void {\
  this.coursesSignal.update(courses =\> courses.map(course =\>
  this.assignCategoryToCourse(course)));\
  }\
  \
  private assignCategoryToCourse(course: Course): Course {\
  const categoryId = course.categoryId ?? 0;\
  course.category = categoryId ? this.getCategoryById(categoryId)() ?? null :
  null;\
  return course;\
  }\
  \
  /\*\*\
  \* Formats error messages for user-friendly display.\
  \* \@param error - The error object.\
  \* \@param fallback - The fallback error message.\
  \* \@returns A formatted error message.\
  \*/\
  private formatError(error: any, fallback: string): string {\
  if (error instanceof Error) {\
  return error.message.includes(\'Resource not found\') ? \`\${fallback}: Not
  found\` : error.message;\
  }\
  return fallback;\
  }\
  }
  ------------------------------------------------------------------------------

  ------------------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(learning-store): add get-course-by-id method and
  re-enable category assignment logic.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update i18n files

-   Update file en.json

  -----------------------------------------------------------------------
  {\
  \"option\": {\
  \"home\": \"Home\",\
  \"about\": \"About Us\",\
  \"categories\": \"Categories\",\
  \"courses\": \"Courses\"\
  },\
  \"about\": {\
  \"title\": \"About us\",\
  \"content\": \"ACME Learning Center is an Education Platform, part of
  ACME Corporation.\"\
  },\
  \"home\": {\
  \"title\": \"Welcome\",\
  \"content\": \"Welcome to ACME Learning Center.\"\
  },\
  \"page-not-found\": {\
  \"title\": \"Page not found\",\
  \"content\": \"The path \<strong\>{{ invalid_path }}\</strong\> is not
  valid.\",\
  \"go-home\": \"Go Home\"\
  },\
  \"footer\": {\
  \"rights\": \"All rights reserved.\",\
  \"powered-by\": \"Powered by\",\
  \"and\": \"and\"\
  },\
  \"categories\": {\
  \"list-title\": \"Categories\",\
  \"id\": \"ID\",\
  \"name\": \"Name\",\
  \"actions\": \"Actions\",\
  \"new\": \"New Category\",\
  \"edit\": \"Edit\",\
  \"delete\": \"Delete\"\
  },\
  \"category\": {\
  \"new-title\": \"Create New Category\",\
  \"edit-title\": \"Edit Category\",\
  \"name\": \"Name\",\
  \"create\": \"Create Category\",\
  \"update\": \"Update Category\",\
  \"cancel\": \"Cancel\",\
  \"error\": {\
  \"name-required\": \"Name is required\"\
  }\
  },\
  \"courses\": {\
  \"list-title\": \"Courses\",\
  \"id\": \"ID\",\
  \"title\": \"Title\",\
  \"description\": \"Description\",\
  \"category\": \"Category\",\
  \"actions\": \"Actions\",\
  \"new\": \"New Course\",\
  \"edit\": \"Edit\",\
  \"delete\": \"Delete\"\
  },\
  \"course\": {\
  \"new-title\": \"Create New Course\",\
  \"edit-title\": \"Edit Course\",\
  \"title\": \"Title\",\
  \"description\": \"Description\",\
  \"category\": \"Category\",\
  \"create\": \"Create Course\",\
  \"update\": \"Update Course\",\
  \"cancel\": \"Cancel\",\
  \"error\": {\
  \"title-required\": \"Title is required\",\
  \"description-required\": \"Description is required\",\
  \"category-required\": \"Category is required\"\
  }\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Update file es.json

  -----------------------------------------------------------------------
  {\
  \"option\" : {\
  \"home\": \"Inicio\",\
  \"about\": \"Acerca de\",\
  \"categories\": \"Categorías\",\
  \"courses\": \"Cursos\"\
  },\
  \"about\": {\
  \"title\": \"Acerca de nosotros\",\
  \"content\": \"ACME Learning Center es una plataforma educativa, parte
  de ACME Corporation.\"\
  },\
  \"home\": {\
  \"title\": \"Bienvenido\",\
  \"content\": \"Bienvenido a ACME Learning Center.\"\
  },\
  \"page-not-found\": {\
  \"title\": \"Página no encontrada\",\
  \"content\": \"La ruta \<strong\>{{ invalid_path }}\</strong\> es
  inválida.\",\
  \"go-home\": \"Ir a Inicio\"\
  },\
  \"footer\": {\
  \"rights\": \"Todos los derechos reservados.\",\
  \"powered-by\": \"Desarrollado con\",\
  \"and\": \"y\"\
  },\
  \"categories\": {\
  \"list-title\": \"Categorías\",\
  \"id\": \"ID\",\
  \"name\": \"Nombre\",\
  \"actions\": \"Acciones\",\
  \"new\": \"Nueva Categoría\",\
  \"edit\": \"Editar\",\
  \"delete\": \"Eliminar\"\
  },\
  \"category\": {\
  \"new-title\": \"Crear Nueva Categoría\",\
  \"edit-title\": \"Editar Categoría\",\
  \"name\": \"Nombre\",\
  \"create\": \"Crear Categoría\",\
  \"update\": \"Actualizar Categoría\",\
  \"cancel\": \"Cancelar\",\
  \"error\": {\
  \"name-required\": \"El nombre es obligatorio\"\
  }\
  },\
  \"courses\": {\
  \"list-title\": \"Cursos\",\
  \"id\": \"ID\",\
  \"title\": \"Título\",\
  \"description\": \"Descripción\",\
  \"category\": \"Categoría\",\
  \"actions\": \"Acciones\",\
  \"new\": \"Nuevo Curso\",\
  \"edit\": \"Editar\",\
  \"delete\": \"Eliminar\"\
  },\
  \"course\": {\
  \"new-title\": \"Crear Nuevo Curso\",\
  \"edit-title\": \"Editar Curso\",\
  \"title\": \"Título\",\
  \"description\": \"Descripción\",\
  \"category\": \"Categoría\",\
  \"create\": \"Crear Curso\",\
  \"update\": \"Actualizar Curso\",\
  \"cancel\": \"Cancelar\",\
  \"error\": {\
  \"title-required\": \"El título es obligatorio\",\
  \"description-required\": \"La descripción es obligatoria\",\
  \"category-required\": \"La categoría es obligatoria\"\
  }\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(i18n): add multilingual support for categories and
  courses translations.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update [learning.routes.ts‎](https://github.com/upc-pre-202520-1asi0729-sandbox/learning-center/commit/7e51d48b8fc9db2c5688c93a0ee7a6b34f22a000#diff-fd762f506ca8f5bd88094db31aaf611a88642c55916a64695a76580c8fcb6d28)

-   Replace file learning/presentation/views/learning.routes.ts with the
    > following content:

  -----------------------------------------------------------------------
  import {Routes} from \'@angular/router\';\
  \
  const courseList = () =\> import(\'./course-list/course-list\').then(m
  =\> m.CourseList);\
  const courseForm = () =\> import(\'./course-form/course-form\').then(m
  =\> m.CourseForm);\
  const categoryList = () =\>
  import(\'./category-list/category-list\').then(m =\> m.CategoryList);\
  const categoryForm = () =\>
  import(\'./category-form/category-form\').then(m =\> m.CategoryForm);\
  export const learningRoutes: Routes = \[\
  { path: \'courses\', loadComponent: courseList },\
  { path: \'courses/new\', loadComponent: courseForm },\
  { path: \'courses/:id/edit\', loadComponent: courseForm },\
  { path: \'categories\', loadComponent: categoryList },\
  { path: \'categories/new\', loadComponent: categoryForm },\
  { path: \'categories/:id/edit\', loadComponent: categoryForm }\
  \];
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"fix(learning-routes): adjust edit route paths for
  courses and categories to improve url structure.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update CategoryForm

-   Replace learning/presentation/views/category-form/category-form.ts
    > with the following code:

  -----------------------------------------------------------------------
  import {Component, inject} from \'@angular/core\';\
  import {FormBuilder, FormControl, ReactiveFormsModule, Validators} from
  \'@angular/forms\';\
  import {ActivatedRoute, Router} from \'@angular/router\';\
  import {LearningStore} from \'../../../application/learning.store\';\
  import {Category} from \'../../../domain/model/category.entity\';\
  import {MatButtonModule} from \'@angular/material/button\';\
  import {MatFormFieldModule} from \'@angular/material/form-field\';\
  import {MatInputModule} from \'@angular/material/input\';\
  import {TranslatePipe} from \'@ngx-translate/core\';\
  \
  \@Component({\
  selector: \'app-category-form\',\
  imports: \[MatFormFieldModule, MatInputModule, MatButtonModule,
  ReactiveFormsModule, TranslatePipe\],\
  templateUrl: \'./category-form.html\',\
  styleUrl: \'./category-form.css\'\
  })\
  export class CategoryForm {\
  private fb = inject(FormBuilder);\
  private route = inject(ActivatedRoute);\
  private router = inject(Router);\
  private store = inject(LearningStore);\
  \
  form = this.fb.group({\
  name: new FormControl\<string\>(\'\', { nonNullable: true, validators:
  \[Validators.required\] })\
  });\
  isEdit = false;\
  categoryId: number \| null = null;\
  \
  constructor() {\
  this.route.params.subscribe(params =\> {\
  this.categoryId = params\[\'id\'\] ? +params\[\'id\'\] : null;\
  this.isEdit = !!this.categoryId;\
  if (this.isEdit && this.categoryId) {\
  let id = this.categoryId;\
  const category = this.store.getCategoryById(id)();\
  if (category) {\
  this.form.patchValue({ name: category.name });\
  }\
  }\
  });\
  }\
  \
  submit() {\
  if (this.form.invalid) return;\
  \
  const category: Category = new Category({\
  id: this.categoryId ?? 0,\
  name: this.form.value.name!\
  });\
  \
  if (this.isEdit) {\
  this.store.updateCategory(category);\
  } else {\
  this.store.addCategory(category);\
  }\
  \
  this.router.navigate(\[\'learning/categories\'\]).then();\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace learning/presentation/views/category-form/category-form.html
    > with the following code:

  -----------------------------------------------------------------------
  \<**h1** class=\"title\"\>{{ (isEdit ? \'category.edit-title\' :
  \'category.new-title\') \| translate }}\</**h1**\>\
  \<**form** \[formGroup\]=\"form\" (ngSubmit)=\"submit()\"\>\
  \<**mat-form-field**\>\
  \<**mat-label**\>{{ \'category.name\'\|translate }}\</**mat-label**\>\
  \<**input** matInput formControlName=\"name\" required\>\
  \@if (form.get(\'name\')!.touched &&
  form.get(\'name\')!.hasError(\'required\')) {\
  \<**mat-error**\>{{ \'category.error.name-required\' \| translate
  }}\</**mat-error**\>\
  }\
  \</**mat-form-field**\>\
  \<**button** mat-raised-button color=\"primary\" type=\"submit\"
  \[disabled\]=\"form.invalid\"\>\
  {{ (isEdit ? \'category.update\' : \'category.create\') \| translate
  }}\
  \</**button**\>\
  \</**form**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace file
    > learning/presentation/views/category-form/category-form.css with
    > the following code:

  -----------------------------------------------------------------------
  .title {\
  margin: 16px;\
  }\
  form {\
  display: flex;\
  flex-direction: column;\
  gap: 16px;\
  max-width: 600px;\
  margin: 16px;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(category-form): ensure proper category retrieval
  by validating category-id. and add i18n support and improve UI
  styling.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update CategoryList

-   Replace file
    > learning/presentation/views/category-list/category-list.ts with
    > the following code:

  -----------------------------------------------------------------------
  import {AfterViewChecked, Component, computed, inject, ViewChild} from
  \'@angular/core\';\
  import {Router} from \'@angular/router\';\
  import {MatButtonModule} from \'@angular/material/button\';\
  import {MatTableDataSource, MatTableModule} from
  \'@angular/material/table\';\
  import {LearningStore} from \'../../../application/learning.store\';\
  import {MatError} from \'@angular/material/form-field\';\
  import {MatProgressSpinner} from
  \'@angular/material/progress-spinner\';\
  import {TranslatePipe} from \'@ngx-translate/core\';\
  import {MatIcon} from \'@angular/material/icon\';\
  import {MatPaginator} from \'@angular/material/paginator\';\
  import {MatSort, MatSortHeader} from \'@angular/material/sort\';\
  \
  \@Component({\
  selector: \'app-category-list\',\
  imports: \[MatTableModule, MatButtonModule, MatError,
  MatProgressSpinner, TranslatePipe, MatIcon, MatPaginator, MatSort,
  MatSortHeader\],\
  templateUrl: \'./category-list.html\',\
  styleUrl: \'./category-list.css\'\
  })\
  export class CategoryList implements AfterViewChecked {\
  readonly store = inject(LearningStore);\
  protected router = inject(Router);\
  \
  displayedColumns: string\[\] = \[\'id\', \'name\', \'actions\'\];\
  \
  \@ViewChild(MatSort) sort!: MatSort;\
  \@ViewChild(MatPaginator) paginator!: MatPaginator;\
  \
  dataSource = computed(() =\> {\
  const source = new MatTableDataSource(this.store.categories());\
  source.sort = this.sort;\
  source.paginator = this.paginator;\
  return source;\
  });\
  \
  editCategory(id: number) {\
  this.router.navigate(\[\'learning/categories\', id,
  \'edit\'\]).then();\
  }\
  \
  deleteCategory(id: number) {\
  this.store.deleteCategory(id);\
  }\
  \
  navigateToNew() {\
  this.router.navigate(\[\'learning/categories/new\'\]).then();\
  }\
  \
  ngAfterViewChecked() {\
  if (this.dataSource().paginator !== this.paginator) {\
  this.dataSource().paginator = this.paginator;\
  }\
  if (this.dataSource().sort !== this.sort) {\
  this.dataSource().sort = this.sort;\
  }\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace file
    > learning/presentation/views/category-list/category-list.html with
    > the following code:

  --------------------------------------------------------------------------------------------------
  \<**h1** class=\"title\"\>{{ \'categories.list-title\' \| translate }}\</**h1**\>\
  \@if (store.loading()) {\
  \<**mat-spinner** diameter=\"40\"\>\</**mat-spinner**\>\
  }\
  \@if (store.error()) {\
  \<**mat-error**\>{{ store.error() }}\</**mat-error**\>\
  }\
  \<**table** mat-table \[dataSource\]=\"dataSource()\" class=\"mat-elevation-z8\" matSort
  matSortActive=\"id\" matSortDirection=\"asc\" matSortDisableClear\>\
  \<!\-- ID Column \--\>\
  \<**ng-container** matColumnDef=\"id\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef mat-sort-header\>{{ \'categories.id\' \| translate
  }}\</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let category\"\> {{ category.id }} \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Name Column \--\>\
  \<**ng-container** matColumnDef=\"name\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef mat-sort-header\> {{ \'categories.name\' \| translate
  }} \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let category\"\> {{ category.name }} \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Actions Column \--\>\
  \<**ng-container** matColumnDef=\"actions\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef\> {{\'categories.actions\' \| translate }}\</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let category\"\>\
  \<**button** mat-icon-button aria-label=\"{{ \'categories.edit\' \| translate }}\"
  (click)=\"editCategory(category.id)\"\>\<**mat-icon**\>edit\</**mat-icon**\>\</**button**\>\
  \<**button** mat-icon-button aria-label=\"{{ \'categories.delete\' \| translate }}\"
  (click)=\"deleteCategory(category.id)\"\>\<**mat-icon**\>delete\</**mat-icon**\>\</**button**\>\
  \</**td**\>\
  \</**ng-container**\>\
  \
  \<**tr** mat-header-row \*matHeaderRowDef=\"displayedColumns\"\>\</**tr**\>\
  \<**tr** mat-row \*matRowDef=\"let row; columns: displayedColumns;\"\>\</**tr**\>\
  \</**table**\>\
  \<**mat-paginator** \[pageSizeOptions\]=\"\[5, 10, 20\]\"
  showFirstLastButtons\>\</**mat-paginator**\>\
  \
  \<**button** mat-raised-button color=\"primary\" (click)=\"navigateToNew()\"\>{{
  \'categories.new\' \| translate }}\</**button**\>
  --------------------------------------------------------------------------------------------------

  --------------------------------------------------------------------------------------------------

-   Replace learning/presentation/views/category-list/category-list.css
    > with the following code:

  -----------------------------------------------------------------------
  .title {\
  margin: 16px;\
  }\
  \
  .mat-table {\
  width: 100%;\
  margin-bottom: 16px;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(category-list): implement table sorting,
  pagination, and i18n support.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update CourseAssembler

-   Replace file learning/infrastructure/course-assembler.ts with the
    > following code:

  -----------------------------------------------------------------------
  import {CourseResource, CoursesResponse} from \'./courses-response\';\
  import {Course} from \'../domain/model/course.entity\';\
  import {BaseAssembler} from
  \'../../shared/infrastructure/base-assembler\';\
  \
  /\*\*\
  \* Assembler for converting between Course entities, CourseResource
  resources, and CoursesResponse.\
  \*/\
  export class CourseAssembler implements BaseAssembler\<Course,
  CourseResource, CoursesResponse\> {\
  /\*\*\
  \* Converts a CoursesResponse to an array of Course entities.\
  \* \@param response - The API response containing courses.\
  \* \@returns An array of Course entities.\
  \*/\
  toEntitiesFromResponse(response: CoursesResponse): Course\[\] {\
  console.log(response);\
  return response.courses.map(resource =\>
  this.toEntityFromResource(resource as CourseResource));\
  }\
  \
  /\*\*\
  \* Converts a CourseResource to a Course entity.\
  \* \@param resource - The resource to convert.\
  \* \@returns The converted Course entity.\
  \*/\
  toEntityFromResource(resource: CourseResource): Course {\
  return new Course({\
  id: resource.id,\
  title: resource.title,\
  description: resource.description,\
  categoryId: resource.categoryId\
  });\
  }\
  \
  /\*\*\
  \* Converts a Course entity to a CourseResource.\
  \* \@param entity - The entity to convert.\
  \* \@returns The converted CourseResource.\
  \*/\
  toResourceFromEntity(entity: Course): CourseResource {\
  return {\
  id: entity.id,\
  title: entity.title,\
  description: entity.description,\
  categoryId: entity.categoryId\
  } as CourseResource;\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(course-assembler): include categoryId in course
  resource assembly.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update CourseForm

-   Replace learning/presentation/views/course-form/course-form.ts with
    > the following code:

  -----------------------------------------------------------------------
  import {Component, inject} from \'@angular/core\';\
  import {FormBuilder, FormControl, ReactiveFormsModule, Validators} from
  \'@angular/forms\';\
  import {ActivatedRoute, Router} from \'@angular/router\';\
  import {LearningStore} from \'../../../application/learning.store\';\
  import {Course} from \'../../../domain/model/course.entity\';\
  import {MatFormFieldModule} from \'@angular/material/form-field\';\
  import {MatSelectModule} from \'@angular/material/select\';\
  import {MatButtonModule} from \'@angular/material/button\';\
  import {MatInput} from \'@angular/material/input\';\
  import {TranslatePipe} from \'@ngx-translate/core\';\
  \
  \@Component({\
  selector: \'app-course-form\',\
  imports: \[\
  ReactiveFormsModule,\
  MatFormFieldModule,\
  MatSelectModule,\
  MatButtonModule,\
  MatInput,\
  TranslatePipe\
  \],\
  templateUrl: \'./course-form.html\',\
  styleUrl: \'./course-form.css\'\
  })\
  export class CourseForm {\
  private fb = inject(FormBuilder);\
  private route = inject(ActivatedRoute);\
  private router = inject(Router);\
  private store = inject(LearningStore);\
  \
  form = this.fb.group({\
  title: new FormControl\<string\>(\'\', { nonNullable: true, validators:
  \[Validators.required\] }),\
  description: new FormControl\<string\>(\'\', { nonNullable: true,
  validators: \[Validators.required\] }),\
  categoryId: new FormControl\<number \| null\>(null)\
  });\
  categories = this.store.categories;\
  isEdit = false;\
  courseId: number \| null = null;\
  \
  constructor() {\
  this.route.params.subscribe(params =\> {\
  this.courseId = params\[\'id\'\] ? +params\[\'id\'\] : null;\
  this.isEdit = !!this.courseId;\
  if (this.isEdit && this.courseId) {\
  let id = this.courseId;\
  const course = this.store.getCourseById(id)();\
  if (course) {\
  this.form.patchValue({\
  title: course.title,\
  description: course.description,\
  categoryId: course.categoryId\
  });\
  }\
  }\
  });\
  }\
  \
  submit() {\
  if (this.form.invalid) return;\
  const course: Course = new Course({\
  id: this.courseId ?? 0,\
  title: this.form.value.title!,\
  description: this.form.value.description!,\
  categoryId: this.form.value.categoryId ?? 0\
  });\
  \
  if (this.isEdit) {\
  this.store.updateCourse(course);\
  } else {\
  this.store.addCourse(course);\
  }\
  \
  this.router.navigate(\[\'learning/courses\'\]).then();\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace learning/presentation/views/course-form/course-form.html
    > with the following code:

  -----------------------------------------------------------------------
  \<**h1** class=\"title\"\>{{ (isEdit ? \'course.edit-title\' :
  \'course.new-title\') \| translate }}\</**h1**\>\
  \<**form** \[formGroup\]=\"form\" (ngSubmit)=\"submit()\"\>\
  \<**mat-form-field**\>\
  \<**mat-label**\>{{ \'course.title\' \| translate }}\</**mat-label**\>\
  \<**input** matInput formControlName=\"title\" required\>\
  \@if (form.get(\'title\')?.touched &&
  form.get(\'title\')!.hasError(\'required\')) {\
  \<**mat-error**\>{{ \'course.error.title-required\' \| translate
  }}\</**mat-error**\>\
  }\
  \</**mat-form-field**\>\
  \
  \<**mat-form-field**\>\
  \<**mat-label**\>{{ \'course.description\' \|
  translate}}\</**mat-label**\>\
  \<**input** matInput formControlName=\"description\" required\>\
  \@if (form.get(\'description\')?.touched &&
  form.get(\'description\')!.hasError(\'required\')) {\
  \<**mat-error**\>{{ \'course.error.description-required\' \| translate
  }}\</**mat-error**\>\
  }\
  \</**mat-form-field**\>\
  \
  \<**mat-form-field**\>\
  \<**mat-label**\>{{ \'course.category\' \|
  translate}}\</**mat-label**\>\
  \<**mat-select** formControlName=\"categoryId\"\>\
  \<**mat-option** \[value\]=\"null\"\>None\</**mat-option**\>\
  \@for (category of categories(); track category.id) {\
  \<**mat-option** \[value\]=\"category.id\"\>{{ category.name
  }}\</**mat-option**\>\
  }\
  \</**mat-select**\>\
  \</**mat-form-field**\>\
  \
  \<**button** mat-raised-button color=\"primary\" type=\"submit\"
  \[disabled\]=\"form.invalid\"\>\
  {{ (isEdit ? \'course.update\' : \'course.create\') \| translate }}\
  \</**button**\>\
  \</**form**\>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace file learning/presentation/views/course-form/course-form.css
    > with the following code:

  -----------------------------------------------------------------------
  .title {\
  margin: 16px;\
  }\
  \
  form {\
  display: flex;\
  flex-direction: column;\
  gap: 16px;\
  max-width: 600px;\
  margin: 16px;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(course-form): simplify category retrieval logic
  and integrate i18n support for labels, titles, and error messages.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Update CourseList

-   Replace file learning/presentation/views/course-list/course-list.ts
    > with the following code:

  -----------------------------------------------------------------------
  import {AfterViewChecked, Component, computed, inject, ViewChild} from
  \'@angular/core\';\
  import {LearningStore} from \'../../../application/learning.store\';\
  import {Router} from \'@angular/router\';\
  import {MatError} from \'@angular/material/form-field\';\
  import {\
  MatCell,\
  MatCellDef,\
  MatColumnDef,\
  MatHeaderCell,\
  MatHeaderCellDef,\
  MatHeaderRow,\
  MatHeaderRowDef,\
  MatRow,\
  MatRowDef,\
  MatTable,\
  MatTableDataSource\
  } from \'@angular/material/table\';\
  import {MatButton, MatIconButton} from \'@angular/material/button\';\
  import {MatProgressSpinner} from
  \'@angular/material/progress-spinner\';\
  import {TranslatePipe} from \'@ngx-translate/core\';\
  import {MatIcon} from \'@angular/material/icon\';\
  import {MatSort, MatSortHeader} from \'@angular/material/sort\';\
  import {MatPaginator} from \'@angular/material/paginator\';\
  \
  \@Component({\
  selector: \'app-course-list\',\
  imports: \[\
  MatError,\
  MatTable,\
  MatHeaderCellDef,\
  MatCellDef,\
  MatColumnDef,\
  MatHeaderCell,\
  MatCell,\
  MatHeaderRowDef,\
  MatRowDef,\
  MatButton,\
  MatHeaderRow,\
  MatRow,\
  MatProgressSpinner,\
  TranslatePipe,\
  MatIcon,\
  MatIconButton,\
  MatSort,\
  MatSortHeader,\
  MatPaginator\
  \],\
  templateUrl: \'./course-list.html\',\
  styleUrl: \'./course-list.css\'\
  })\
  export class CourseList implements AfterViewChecked {\
  readonly store = inject(LearningStore);\
  protected router = inject(Router);\
  \
  displayedColumns: string\[\] = \[\'id\', \'title\', \'description\',
  \'category\', \'actions\'\];\
  \
  \@ViewChild(MatSort) sort!: MatSort;\
  \@ViewChild(MatPaginator) paginator!: MatPaginator;\
  \
  dataSource = computed(() =\> {\
  const source = new MatTableDataSource(this.store.courses());\
  source.sort = this.sort;\
  source.paginator = this.paginator;\
  return source;\
  });\
  \
  editCourse(id: number) {\
  this.router.navigate(\[\'learning/courses\', id, \'edit\'\]).then();\
  }\
  \
  deleteCourse(id: number) {\
  this.store.deleteCourse(id);\
  }\
  \
  navigateToNew() {\
  this.router.navigate(\[\'learning/courses/new\'\]).then();\
  }\
  \
  ngAfterViewChecked() {\
  if (this.dataSource().paginator !== this.paginator) {\
  this.dataSource().paginator = this.paginator;\
  }\
  if (this.dataSource().sort !== this.sort) {\
  this.dataSource().sort = this.sort;\
  }\
  }\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Replace file
    > learning/presentation/views/course-list/course-list.html with the
    > following code:

  ----------------------------------------------------------------------------------------------
  \<**h1** class=\"title\"\>{{ \'courses.list-title\' \| translate }}\</**h1**\>\
  \@if (store.loading()) {\
  \<**mat-spinner** diameter=\"40\"\>\</**mat-spinner**\>\
  }\
  \@if (store.error()) {\
  \<**mat-error**\>{{ store.error() }}\</**mat-error**\>\
  }\
  \<**table** mat-table \[dataSource\]=\"dataSource()\" class=\"mat-elevation-z8\" matSort
  matSortActive=\"id\" matSortDirection=\"asc\" matSortDisableClear\>\
  \<!\-- ID Column \--\>\
  \<**ng-container** matColumnDef=\"id\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef mat-sort-header\>{{ \'courses.id\' \|
  translate}}\</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let course\"\> {{ course.id }} \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Title Column \--\>\
  \<**ng-container** matColumnDef=\"title\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef mat-sort-header\>{{ \'courses.title\' \|
  translate}}\</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let course\"\> {{ course.title }} \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Description Column \--\>\
  \<**ng-container** matColumnDef=\"description\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef mat-sort-header\> {{ \'courses.description\' \|
  translate}} \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let course\"\> {{ course.description }} \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Category Column \--\>\
  \<**ng-container** matColumnDef=\"category\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef mat-sort-header\> {{ \'courses.category\' \|
  translate }} \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let course\"\> {{ course.category?.name ?? \'None\' }}
  \</**td**\>\
  \</**ng-container**\>\
  \
  \<!\-- Actions Column \--\>\
  \<**ng-container** matColumnDef=\"actions\"\>\
  \<**th** mat-header-cell \*matHeaderCellDef\> {{ \'courses.actions\' \| translate }}
  \</**th**\>\
  \<**td** mat-cell \*matCellDef=\"let course\"\>\
  \<**button** mat-icon-button aria-label=\"{{ \'courses.edit\' \| translate }}\"
  (click)=\"editCourse(course.id)\"\>\<**mat-icon**\>edit\</**mat-icon**\>\</**button**\>\
  \<**button** mat-icon-button aria-label=\"{{ \'courses.delete\' \| translate }}\"
  (click)=\"deleteCourse(course.id)\"\>\<**mat-icon**\>delete\</**mat-icon**\>\</**button**\>\
  \</**td**\>\
  \</**ng-container**\>\
  \
  \<**tr** mat-header-row \*matHeaderRowDef=\"displayedColumns\"\>\</**tr**\>\
  \<**tr** mat-row \*matRowDef=\"let row; columns: displayedColumns;\"\>\</**tr**\>\
  \</**table**\>\
  \
  \<**mat-paginator** \[pageSizeOptions\]=\"\[5, 10, 20\]\"
  showFirstLastButtons\>\</**mat-paginator**\>\
  \
  \<**button** mat-raised-button color=\"primary\" (click)=\"navigateToNew()\"\>{{
  \'courses.new\' \| translate }}\</**button**\>
  ----------------------------------------------------------------------------------------------

  ----------------------------------------------------------------------------------------------

-   Replace learning/presentation/views/course-list/course-list.css with
    > the following code:

  -----------------------------------------------------------------------
  .title {\
  margin: 16px;\
  }\
  \
  .mat-table {\
  width: 100%;\
  margin-bottom: 16px;\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(course-list): add sorting, pagination, and i18n
  for improved usability.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# MockAPI

-   Create Web App for mockapi uploading github repo

![](media/image9.png){width="6.267716535433071in"
height="7.541666666666667in"}

![](media/image3.png){width="6.267716535433071in" height="7.5in"}

![](media/image4.png){width="4.909346019247594in"
height="3.8473403324584425in"}

![](media/image8.png){width="4.281477471566054in"
height="5.466876640419947in"}

-   Make sure set SCM Basic Auth to On:

![](media/image1.png){width="6.267716535433071in"
height="4.277777777777778in"}

-   Download publish profile

![](media/image2.png){width="6.267716535433071in"
height="2.2777777777777777in"}

-   Update github action workflow main_mockapi2.yml

-   Create a new repository secret in github repo:
    > AZURE_WEBAPP_PUBLISH_PROFILE

> ![](media/image5.png){width="6.267716535433071in"
> height="4.027777777777778in"}
>
> [[https://mockapi7349.azurewebsites.net]{.underline}](https://mockapi7349.azurewebsites.net)

-   Replace environment.ts with the following content:

  -----------------------------------------------------------------------
  export const environment = {\
  production: true,\
  platformProviderApiBaseUrl:
  \'https://mockapi.azurewebsites.net/api/v1\',\
  platformProviderCategoriesEndpointPath: \'/categories\',\
  platformProviderCoursesEndpointPath: \'/courses\',\
  logoProviderApiBaseUrl: \'https://logo.clearbit.com/\'\
  };
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"feat(environments): update api base url in
  production.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Generate production build

  -----------------------------------------------------------------------
  ng build \--configuration=production
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Install lite-server

  -----------------------------------------------------------------------
  npm install -g lite-server
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Serve the production build locally with lite-server

  -----------------------------------------------------------------------
  lite-server \--baseDir=\"dist/learning-center/browser\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

# Deployment

-   Right-click on src folder → New → File

Name the file routes.json and press Enter

Add the following code:

  -----------------------------------------------------------------------
  {\
  \"routes\": \[\
  {\
  \"route\": \"/\*\",\
  \"serve\": \"/index.html\",\
  \"statusCode\": 200\
  }\
  \]\
  }
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Update angular.json to add \'src/routes.json\' in the assets
    > section:

  -----------------------------------------------------------------------
  \"assets\": \[\
  {\
  \"glob\": \"\*\*/\*\",\
  \"input\": \"public\"\
  },\
  \"src/routes.json\"\
  \],
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Commit

  -----------------------------------------------------------------------
  git add .\
  git commit -m \"chore: configure rewrite rule for SPA.\"
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Generate production build

  -----------------------------------------------------------------------
  ng build \--configuration=production
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

-   Create static web app in Azure

> **Output location/Ubicación de salida:**
>
> dist/learning-center/browser
>
> ![](media/image7.png){width="3.07in" height="4.764795494313211in"}
