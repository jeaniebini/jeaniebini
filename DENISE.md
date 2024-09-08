ACT1
import 'dart:io';
void main(){
List <String> inventory = ['apple', 'banana', 'carrot', 'dates'];

print('Initial Inventory: $inventory');
print('');
print('Please select an operation to do:');
print('[1] Add New Product in the inventory');
print('[2] Remove a Product from the inventory');
print('[3] Display the total number of items in the inventory');
print('[4] Allow the user to search for an item and display if it is available or not');
print('[5] Sort the inventory list alphabetically');
print('[6] Exit');
print("");

  while (true) {
    stdout.write('You have selected:');
    String? selectedNum = stdin.readLineSync();

  switch (selectedNum){
    case '1':
      stdout.write('Please enter the product you want to add on the list:');
      String? newProduct = stdin.readLineSync();
      if (newProduct != null && newProduct.isNotEmpty){
        inventory.add(newProduct);
        print('Updated Inventory after adding: $inventory');
      }
      break;

    case '2':
      stdout.write('Please enter the product you want to remove on the list:');
      String? removeProduct = stdin.readLineSync();
      if (removeProduct != null && inventory.contains(removeProduct)){
        inventory.remove(removeProduct);
        print('Updated Inventory after removal: $inventory');
      }else{
        print('$removeProduct not found in the inventory.');
      }
      break;

    case '3':
      print('Total number of items in inventory: ${inventory.length}');
      break;

    case '4':
      stdout.write('Enter a product to search:');
      String? searchProduct = stdin.readLineSync();
      if (searchProduct != null && inventory.contains(searchProduct)){
        print('$searchProduct is available in the inventory.');
      }else{
        print('$searchProduct is not available in the inventory.');
      }
      break;

    case '5':
      inventory.sort();
      print('Sort Inventory: $inventory');
      break;

    case '6':
      print('Exiting...');
      exit(0);

    default:
      stdout.write('Invalid input. Please select a valid number:');
    }
  }
}

ACT2
import 'dart:io';
void main(){
List <String> inventory = ['apple', 'banana', 'carrot', 'dates'];

print('Initial Inventory: $inventory');
print('');
print('Please select an operation to do:');
print('[1] Add New Product in the inventory');
print('[2] Remove a Product from the inventory');
print('[3] Display the total number of items in the inventory');
print('[4] Allow the user to search for an item and display if it is available or not');
print('[5] Sort the inventory list alphabetically');
print('[6] Exit');
print("");

  while (true) {
    stdout.write('You have selected:');
    String? selectedNum = stdin.readLineSync();

  switch (selectedNum){
    case '1':
      addProduct(inventory);
      break;

    case '2':
      removeProduct(inventory);
      break;

    case '3':
      print('Total number of items in inventory: ${getTotalItems(inventory)}');
      break;

    case '4':
      bool available = isProductAvailable(inventory);
      if (available){
        print('The Product is available in the inventory.');
        }else{
        print('The product is not available in the inventory.');
        }
      break;

    case '5':
      sortInventory(inventory);
      break;

    case '6':
      print('Exiting...');
      exit(0);

    default:
    stdout.write('Invalid input. Please select a valid number:');
    }
  }
}

void addProduct(List inventory){
stdout.write('Please enter the product you want to add on the list:');
String? newProduct = stdin.readLineSync();
if (newProduct != null && newProduct.isNotEmpty){
  inventory.add(newProduct);
  print('Updated Inventory after adding: $inventory');
}
}

void removeProduct(List inventory){
stdout.write('Please enter the product you want to remove on the list:');
String? removeProduct = stdin.readLineSync();
if (removeProduct != null && inventory.contains(removeProduct)){
  inventory.remove(removeProduct);
  print('Updated Inventory after removal: $inventory');
}else{
  print('$removeProduct not found in the inventory.');
}
}

int getTotalItems(List inventory){
return inventory.length;
}

bool isProductAvailable(List inventory){
stdout.write('Enter a product to search:');
String? searchProduct = stdin.readLineSync();
return searchProduct != null && inventory.contains(searchProduct);
}

void sortInventory(List inventory){
inventory.sort();
print('Sort Inventory: $inventory');
}
