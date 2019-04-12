# :) Unsubscribe para Pros and Juniors 💪 💨

#### Português 😁
 Decorador de classe que irá automaticamente cancelar os observáveis ​​quando o componente for destruído e não só  .

#### English 👳
 Class decorator that will automatically unsubscribe from observable subscriptions when the component is destroyed .

## Installation ⚡️

`npm install ngx-leave --save`


## Usage   AutoLeave

```js
import {AutoLeave} from "ngx-leave";

@AutoLeave()
@Component({
  selector: 'app'
})
export class appComponent  implements OnInit, OnDestroy{
  um$: Subscription;
  dois$: Subscription;

  constructor(  ) {  }

  ngOnInit() {

    const mapSource = from(map).subscribe(val => console.log(val));
    this.um$ = Rx.Observable.create(o=>this.myObserver = o);


  }

  // Este metodo deve ser sempre criado mesmo que ele esteja vazio.
  ngOnDestroy() {
    // Caso esse metodo não for declarado vai retornar um erro
  }
}
```



###

| Opções      | Descrição                                              | Value inicial |
| ----------- | ------------------------------------------------------ | ------------- |
| `arrayName` | unsubscribe para subscriptions  especificado no array  | `''`          |
| `blackList` | Um array de propriedades a serem excluidas             | `[]`          |
| `evento`     | nome do evento que sera chamado                        | `ngOnDestroy` |

Nota: `blackList` sera iginorado se `arrayName` tiver algum valor definido.

`@AutoLeave(["um$", "dois$"])`

## Usando Leave

```ts
import {Leave} from 'ngx-leave';

@Component({
  selector: 'app-test',
  templateUrl: './test.component.html',
})
export class testComponent implements OnInit, OnDestroy {

constructor(  ) {  }

 ngOnInit() {
    interval(1000)
      .pipe(Leave(this))
      .subscribe(val => console.log(val));
  }

  // Este metodo deve ser sempre criado mesmo que ele esteja vazio.
  ngOnDestroy() {
    // Caso esse metodo não for declarado vai retornar um erro
  }
}
```

### Opções

Leave(this,FunctionName);

### Usando em uma class

```ts
import {Leave} from 'ngx-leave';

export class Widget {
  constructor() {
    interval(1000)
      .pipe(Leave(this, 'elimina'))
      .subscribe(console.log);
  }

  // A string name do segundo parametro deve ser sempre o mesmo nome da função
  elimina() {}
}
```


We test  💕 💞

| Ação        | Descrição
| ----------- | ------------------ |
| `Test Suite`| 1 passed, 1 total  |
| `Tests`     | 7 passed, 7 total  |
| `Snapshots` | 0 total            |
| `Time`      | 4.129s             |
| `Ran all test suites`            |




### Obrigado  👊 👊 ✊ ✌️
All Devs {no java 👽 😂  😂 }


