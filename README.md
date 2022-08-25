# Implementation-Binary-Tree
Implementation binary tree and traverse


package game.main;

import java.util.Scanner;

public class BinaryTree {

    static Scanner sc = null;

    public static void main(String[] args) {
        sc = new Scanner(System.in);
        Node root = createTree();
        InOreder(root);
        System.out.println();
        PreOreder(root);
        System.out.println();
        PosteOreder(root);
        System.out.println();

    }

    static Node createTree() {
        Node root = null;
        System.out.println("Enter data:");
        int data = sc.nextInt();

        if (data == -1) return null;

        root = new Node(data);

        System.out.println("Enter left for" + data);
        root.left = createTree();

        System.out.println("Eneter rigth for" + data);
        root.rigth = createTree();

        return root;
    }

    static void InOreder(Node root) {
        if (root == null) return;
        InOreder(root.left);
        System.out.println(root.data + " ");
        InOreder(root.rigth);
    }

    static void PreOreder(Node root) {
        if (root == null) return;
        System.out.println(root.data + " ");

        PreOreder(root.left);
        PreOreder(root.rigth);
    }

    static void PosteOreder(Node root) {
        if (root == null) return;

        PosteOreder(root.left);
        PosteOreder(root.rigth);
        System.out.println(root.data + " ");
    }


    static class Node {
        Node left, rigth;
        int data;

        public Node(int data) {
            this.data = data;
        }
    }
}

