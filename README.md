# -Setting-up-landing
цу робтися для того якщо у вас будуть помилкі в коді то щоб неможливо було закомітити на гітхаб 
(во время коміта прогоняються тести і ліндінг і якщо щось з цього не проходить тоді і коміт не пройде)

Встановити залежність
npm install --save-dev prettier husky lint-staged

Далі створюємо 3 файли в корне нашого проекту
Першій файл -
.huskyrc
1 {
    "hooks": {
        "pre-commit": "lint-staged"
    }
}

Другий файл - 
.lintstagedrc
{
    "src/**/*.{json,css,scss,md}": {"prettier --write"},
    "src/**/*.{js,jsx,ts,tsx}": {"prettier --write", "eslint --fix"}
}

Третій - 
.prettierrc.json
{
    "printWidth": 80,
    "tabWidth": 2,
    "useTabs": false,
    "semi": true,
    "singleQuote": true,
    "trailingComma": "all",
    "bracketSpacing": true,
    "jsxBracketSameLine": false,
    "arrowParens": "avoid",
    "proseWrap": "always"
  }

  і останій шаг це налаштування в VSCode
  заходимо в налаштування і пишемо строку - codeActionsOnSave
  і додаємо потім в джейсон фомат 
  "editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
  }

