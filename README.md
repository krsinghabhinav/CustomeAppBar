# CustomeAppBar

import 'package:flutter/material.dart';

class CustomAppBar extends StatelessWidget implements PreferredSizeWidget {
  final String title;
  final List<Widget>? actions;
  final Color backgroundColor;
  final Widget? leading;

  CustomAppBar({
    required this.title,
    this.actions,
    this.backgroundColor = Colors.blue,
    this.leading,
  });

  @override
  Widget build(BuildContext context) {
    return AppBar(
      backgroundColor: backgroundColor,
      title: Text(
        title,
        style: TextStyle(color: Colors.white),
      ),
      leading: leading,
      actions: actions,
      centerTitle: true, // Center the title
      elevation: 4, // Add shadow to the AppBar
    );
  }

  @override
  Size get preferredSize => Size.fromHeight(45.0); // Standard AppBar height
}
===================================================================
import 'package:flutter/material.dart';
import 'custom_appbar.dart'; // Import your custom AppBar file

class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: CustomAppBar(
        title: "Home",
        backgroundColor: Colors.teal,
        actions: [
          IconButton(
            icon: Icon(Icons.search),
            onPressed: () {
              // Action for search button
            },
          ),
          IconButton(
            icon: Icon(Icons.notifications),
            onPressed: () {
              // Action for notifications button
            },
          ),
        ],
        leading: IconButton(
          icon: Icon(Icons.menu),
          onPressed: () {
            // Action for menu button
          },
        ),
      ),
      body: Center(child: Text("Home Page")),
    );
  }
}
