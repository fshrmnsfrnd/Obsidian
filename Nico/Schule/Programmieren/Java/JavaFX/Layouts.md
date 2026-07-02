---
Thema:
  - "[[JavaFX]]"
---
[[JavaFX]] 
https://docs.oracle.com/javafx/2/layout/builtin_layouts.htm
# Stage
`stage.setTitle("Name")`
`stage.setScene(scene)`
`stage.show()`

# Scene
`var scene = new Scene(Pane, xSize, ySize)`
# Borderpane
>The [`BorderPane`](https://docs.oracle.com/javafx/2/api/javafx/scene/layout/BorderPane.html) layout pane provides five regions in which to place nodes: top, bottom, left, right, and center. The following picture shows the type of layout that you can create with a border pane. The regions can be any size. If your application does not need one of the regions, you do not need to define it and no space is allocated for it.

![[Pasted image 20250411090614.png]]
```java
BorderPane borderPane = new BorderPane();
borderPane.setTop(Object);
borderPane.setCenter(Object);
borderPane.setBottom(Object);
borderPane.setLeft(Object);
borderPane.setRight(Object);
```

# GridPane
>The [`GridPane`](https://docs.oracle.com/javafx/2/api/javafx/scene/layout/GridPane.html) layout pane enables you to create a flexible grid of rows and columns in which to lay out nodes. Nodes can be placed in any cell in the grid and can span cells as needed. A grid pane is useful for creating forms or any layout that is organized in rows and columns. [Figure 1-8](https://docs.oracle.com/javafx/2/layout/builtin_layouts.htm#CHDFCFAE) shows a grid pane that contains an icon, title, subtitle, text and a pie chart. In this figure, the `gridLinesVisible` property is set to display grid lines, which show the rows and columns and the gaps between the rows and columns. This property is useful for visually debugging your `GridPane` layouts.

```java
GridPane grid = new GridPane();
grid.setHgap(10);
grid.setVgap(10);
grid.setPadding(new Insets(0, 10, 0, 10));
grid.add(object, xPosition, yPosition)
```

# StackPane
>The [`StackPane`](https://docs.oracle.com/javafx/2/api/javafx/scene/layout/StackPane.html) layout pane places all of the nodes within a single stack with each new node added on top of the previous node. This layout model provides an easy way to overlay text on a shape or image or to overlap common shapes to create a complex shape.

```java
public void addStackPane(HBox hb) {
    StackPane stack = new StackPane();
    Rectangle helpIcon = new Rectangle(30.0, 25.0);
    helpIcon.setFill(new LinearGradient(0,0,0,1, true, CycleMethod.NO_CYCLE,
        new Stop[]{
        new Stop(0,Color.web("#4977A3")),
        new Stop(0.5, Color.web("#B0C6DA")),
        new Stop(1,Color.web("#9CB6CF")),}));
    helpIcon.setStroke(Color.web("#D0E6FA"));
    helpIcon.setArcHeight(3.5);
    helpIcon.setArcWidth(3.5);

    Text helpText = new Text("?");
    helpText.setFont(Font.font("Verdana", FontWeight.BOLD, 18));
    helpText.setFill(Color.WHITE);
    helpText.setStroke(Color.web("#7080A0")); 

    stack.getChildren().addAll(helpIcon, helpText);
    stack.setAlignment(Pos.CENTER_RIGHT);     // Right-justify nodes in stack
    StackPane.setMargin(helpText, new Insets(0, 10, 0, 0)); // Center "?"

    hb.getChildren().add(stack);            // Add to HBox from [Example 1-2]
    HBox.setHgrow(stack, Priority.ALWAYS);    // Give stack any extra space
}
```

# FlowPane
>The nodes within a [`FlowPane`](https://docs.oracle.com/javafx/2/api/javafx/scene/layout/FlowPane.html) layout pane are laid out consecutively and wrap at the boundary set for the pane. Nodes can flow vertically (in columns) or horizontally (in rows). A vertical flow pane wraps at the height boundary for the pane. A horizontal flow pane wraps at the width boundary for the pane. [Figure 1-10](https://docs.oracle.com/javafx/2/layout/builtin_layouts.htm#CHDCACIE) shows a sample horizontal flow pane using numbered icons. By contrast, in a vertical flow pane, column one would contain pages one through four and column two would contain pages five through eight.

![[Pasted image 20250411101023.png]]

```java
public FlowPane addFlowPane() {
    FlowPane flow = new FlowPane();
    flow.setPadding(new Insets(5, 0, 5, 0));
    flow.setVgap(4);
    flow.setHgap(4);
    flow.setPrefWrapLength(170); // preferred width allows for two columns
    flow.setStyle("-fx-background-color: DAE6F3;");

    ImageView pages[] = new ImageView[8];
    for (int i=0; i<8; i++) {
        pages[i] = new ImageView(
            new Image(LayoutSample.class.getResourceAsStream(
            "graphics/chart_"+(i+1)+".png")));
        flow.getChildren().add(pages[i]);
    }

    return flow;
}
```
## HBox
>The [`HBox`](https://docs.oracle.com/javafx/2/api/javafx/scene/layout/HBox.html) layout pane provides an easy way for arranging a series of nodes in a single row.
```java
HBox hbox = new HBox(Element1, Element2, ...);
hbox.setPadding(new Insets(15, 12, 15, 12));
hbox.setSpacing(10);
hbox.setStyle("-fx-background-color: #336699;");
```

## VBox
>The [`VBox`](https://docs.oracle.com/javafx/2/api/javafx/scene/layout/VBox.html) layout pane is similar to the `HBox` layout pane, except that the nodes are arranged in a single column.

`VBox vbox = new VBox(Element1, Element2, ...)`