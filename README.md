# Articles
Articles application

I used T-SQL as Database engine

In order to run the application you must create a database with name ArticlesDb.
After you create the database please run the following script to create the Article table required:

USE [ArticlesDb]
GO

SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[Article](
	[id] [int] IDENTITY(1,1) NOT NULL,
	[title] [nvarchar](max) NULL,
	[content] [nvarchar](max) NULL,
	[publishedDate] [datetime] NULL,
 CONSTRAINT [PK_Article] PRIMARY KEY CLUSTERED 
(
	[id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO

ALTER TABLE [dbo].[Article] ADD  CONSTRAINT [DF_Article_publishedDate]  DEFAULT (getdate()) FOR [publishedDate]
GO


After you create the database and the table you must update the connection string from appsettings.json from the Articles/WebApi project.


