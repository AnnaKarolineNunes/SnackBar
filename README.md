# Criando uma SnackBar

## Descrição

Projeto simples cujo objetivo é criar uma snackbar ( mensagem que é exibida no canto inferior da tela) 

## Capturas de Tela

![image](https://github.com/AnnaKarolineNunes/SnackBar/assets/101477642/e3c32319-1d62-4660-bdc6-3a2c10fe3329)
![image](https://github.com/AnnaKarolineNunes/SnackBar/assets/101477642/1b0330ae-f9f3-4b7b-8135-87ad7e6fd07c)

## Passo a Passo

- Passo 1 : Construir um layout. Neste caso usaremos dois buttons, um para abrir e outro para fechar a snackbar
- Passo 2 : no MainActivity.class , criar os atributos dos dois buttons bem como o método findViewById dentro do método onCreate bem como o atributo snackbar.
  ```
      public class MainActivity extends AppCompatActivity {
        private Button buttonAbrir;
        private Button buttonFechar;
        private Snackbar snackbar;
    
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            buttonAbrir = findViewById(R.id.buttonAbrir);
            buttonFechar = findViewById(R.id.buttonFechar);
        }
    }

- Passo 3 : passar o método setOnClickListener() para que seja possivel clicar no button abrir
   ```
      public class MainActivity extends AppCompatActivity {
        private Button buttonAbrir;
        private Button buttonFechar;
    
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            buttonAbrir = findViewById(R.id.buttonAbrir);
            buttonFechar = findViewById(R.id.buttonFechar);
   
            buttonAbrir.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
    
            }
        });
        }
    }
   
 - Passo 4 : Com o evento de clique criado, devemos confirgurar o recurso snackbar. Note que ele possui 2 parametros +  setAction para configurar um botão ao mesmo.
   ```
   buttonAbrir.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                snackbar = Snackbar.make(
                        view, "Botao pressionado",
                        Snackbar.LENGTH_INDEFINITE
                ).setAction("Confirmar", new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                        buttonAbrir.setText("Botão abrir alterado");
                    }
                });

                snackbar.show();
            }
        });

 - Passo 5 : Por fim, ainda dentro do método onCreate criamos um evento de clique para fechar a snackbar, nessa situação em que a snackbar tem tempo indefinido.
   ```
    buttonFechar.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                snackbar.dismiss();
            }
        });







