import javafx.application.Application;
import javafx.geometry.Insets;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.control.TextField;
import javafx.scene.layout.GridPane;
import javafx.stage.Stage;
 
public class CalculatorApp extends Application {
 
    private TextField display;
    private String operator;
    private double num1;
 
    @Override
    public void start(Stage primaryStage) {
        primaryStage.setTitle("Calculator");
 
        GridPane grid = new GridPane();
        grid.setPadding(new Insets(10, 10, 10, 10));
        grid.setVgap(8);
        grid.setHgap(8);
 
        display = new TextField();
        display.setEditable(false);
        display.setMinSize(300, 50);
        GridPane.setConstraints(display, 0, 0, 4, 1);
 
        createButton(grid, "1", 0, 1);
        createButton(grid, "2", 1, 1);
        createButton(grid, "3", 2, 1);
        createOperatorButton(grid, "+", 3, 1);
 
        createButton(grid, "4", 0, 2);
        createButton(grid, "5", 1, 2);
        createButton(grid, "6", 2, 2);
        createOperatorButton(grid, "-", 3, 2);
 
        createButton(grid, "7", 0, 3);
        createButton(grid, "8", 1, 3);
        createButton(grid, "9", 2, 3);
        createOperatorButton(grid, "*", 3, 3);
 
        createButton(grid, "0", 0, 4);
        createButton(grid, ".", 1, 4);
        createEqualsButton(grid, "=", 2, 4);
        createOperatorButton(grid, "/", 3, 4);
 
        createButton(grid, "sin", 0, 5);
        createButton(grid, "cos", 1, 5);
        createButton(grid, "x^2", 2, 5);
        createButton(grid, "sqrt", 3, 5);
 
        Scene scene = new Scene(grid, 400, 500);
        primaryStage.setScene(scene);
        primaryStage.show();
    }
 
    private void createButton(GridPane grid, String text, int col, int row) {
        Button button = new Button(text);
        button.setOnAction(e -> handleButtonAction(text));
        GridPane.setConstraints(button, col, row);
        grid.getChildren().add(button);
    }
 
    private void createOperatorButton(GridPane grid, String text, int col, int row) {
        Button button = new Button(text);
        button.setOnAction(e -> handleOperator(text));
        GridPane.setConstraints(button, col, row);
        grid.getChildren().add(button);
    }
 
    private void createEqualsButton(GridPane grid, String text, int col, int row) {
        Button button = new Button(text);
        button.setOnAction(e -> calculate());
        GridPane.setConstraints(button, col, row);
        grid.getChildren().add(button);
    }
 
    private void handleButtonAction(String text) {
        // Handle other button actions if needed
        appendText(text);
    }
 
    private void appendText(String text) {
        display.appendText(text);
    }
 
    private void handleOperator(String newOperator) {
        operator = newOperator;
        num1 = Double.parseDouble(display.getText());
        display.clear();
    }
 
    private void calculate() {
        double num2 = Double.parseDouble(display.getText());
        switch (operator) {
            case "+":
                display.setText(String.valueOf(num1 + num2));
                break;
            case "-":
                display.setText(String.valueOf(num1 - num2));
                break;
            case "*":
                display.setText(String.valueOf(num1 * num2));
                break;
            case "/":
                if (num2 != 0) {
                    display.setText(String.valueOf(num1 / num2));
                } else {
                    display.setText("Error");
                }
                break;
            case "sin":
                display.setText(String.valueOf(Math.sin(num2)));
                break;
            case "cos":
                display.setText(String.valueOf(Math.cos(num2)));
                break;
            case "x^2":
                display.setText(String.valueOf(Math.pow(num2, 2)));
                break;
            case "sqrt":
                display.setText(String.valueOf(Math.sqrt(num2)));
                break;
            // Add other cases for more operators...
 
            default:
                break;
        }
    }
 
    public static void main(String[] args) {
        launch(args);
    }
}
