#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 100

// Queue structure
struct Queue {
    int items[MAX_SIZE];
    int front;
    int rear;
};

// Function to initialize the queue
void initializeQueue(struct Queue* queue) {
    queue->front = -1;
    queue->rear = -1;
}

// Function to check if the queue is empty
int isEmpty(struct Queue* queue) {
    return queue->front == -1;
}

// Function to check if the queue is full
int isFull(struct Queue* queue) {
    return (queue->rear + 1) % MAX_SIZE == queue->front;
}

// Function to enqueue (add) an item to the queue
void enqueue(struct Queue* queue, int item) {
    if (isFull(queue)) {
        printf("Queue is full. Cannot enqueue more items.\n");
        return;
    }

    // If the queue is empty, set front to 0
    if (isEmpty(queue)) {
        queue->front = 0;
    }

    // Increment rear and enqueue the item
    queue->rear = (queue->rear + 1) % MAX_SIZE;
    queue->items[queue->rear] = item;

    printf("Print job enqueued: %d\n", item);
}

// Function to dequeue (remove) an item from the queue
int dequeue(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty. Cannot dequeue from an empty queue.\n");
        return -1; // Returning an invalid value for simplicity
    }

    int removedItem = queue->items[queue->front];

    // If there was only one item, reset front and rear
    if (queue->front == queue->rear) {
        queue->front = -1;
        queue->rear = -1;
    } else {
        // Increment front
        queue->front = (queue->front + 1) % MAX_SIZE;
    }

    printf("Print job dequeued: %d\n", removedItem);
    return removedItem;
}

int main() {
    // Initialize the printer queue
    struct Queue printerQueue;
    initializeQueue(&printerQueue);

    // Enqueue print jobs
    enqueue(&printerQueue, 101);
    enqueue(&printerQueue, 102);
    enqueue(&printerQueue, 103);

    // Dequeue and process print jobs
    dequeue(&printerQueue); // Processing 101
    dequeue(&printerQueue); // Processing 102
    dequeue(&printerQueue); // Processing 103
    dequeue(&printerQueue); // Trying to dequeue when the queue is empty

    return 0;
}
