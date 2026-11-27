// Q1 — Create exactly the four mandatory collections.
// Run in mongosh. This script drops only the target database for a clean demo.
use("socialsphere");
db.dropDatabase();

db.createCollection("users", {
  validator: {
    $jsonSchema: {
      bsonType: "object",
      required: ["id", "name", "email", "joinedDate"],
      additionalProperties: false,
      properties: {
        _id: {},
        id: { bsonType: ["int", "long"], description: "Application user ID" },
        name: { bsonType: "string" },
        email: { bsonType: "string" },
        joinedDate: { bsonType: "date" }
      }
    }
  }
});

db.createCollection("posts", {
  validator: {
    $jsonSchema: {
      bsonType: "object",
      required: ["id", "userId", "content", "createdAt", "likeCount"],
      additionalProperties: false,
      properties: {
        _id: {},
        id: { bsonType: ["int", "long"] },
        userId: { bsonType: ["int", "long"] },
        content: { bsonType: "string" },
        createdAt: { bsonType: "date" },
        likeCount: { bsonType: ["int", "long"], minimum: 0 }
      }
    }
  }
});

db.createCollection("comments", {
  validator: {
    $jsonSchema: {
      bsonType: "object",
      required: ["id", "postId", "userId", "commentText", "createdAt"],
      additionalProperties: false,
      properties: {
        _id: {},
        id: { bsonType: ["int", "long"] },
        postId: { bsonType: ["int", "long"] },
        userId: { bsonType: ["int", "long"] },
        commentText: { bsonType: "string" },
        createdAt: { bsonType: "date" }
      }
    }
  }
});

db.createCollection("likes", {
  validator: {
    $jsonSchema: {
      bsonType: "object",
      required: ["id", "postId", "userId", "likedAt"],
      additionalProperties: false,
      properties: {
        _id: {},
        id: { bsonType: ["int", "long"] },
        postId: { bsonType: ["int", "long"] },
        userId: { bsonType: ["int", "long"] },
        likedAt: { bsonType: "date" }
      }
    }
  }
});

print("Collections created:");
printjson(db.getCollectionNames()); // Expected: users, posts, comments, likes
